//ลงทะเบียน ลบตัวเลือกออกเมื่อมีผู้เลือกแล้ว

function myFunction() {
  var form = FormApp.openById('1Lr9HhpqwYr_X7aBo9Nm_xQemDJiwID8jgCHEU77hbh4') // ***ใส่ form id ที่ใช้งาน***
  var data = SpreadsheetApp.getActiveSpreadsheet().getRange('เวลา!A2:C37').getValues() // ***ชื่อซีต ช่วงข้อมูล***
  var choice = []
      for(var i in data){
         if(data[i][0] != "" && data[i][2]>0){
            choice.push(data[i][0])
         }
      }
      var formItem = form.getItems(FormApp.ItemType.LIST)
      formItem[0].asListItem().setChoiceValues(choice)
}
