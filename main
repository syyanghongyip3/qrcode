// 連結HTML檔案



function doGet(){
  var html = HtmlService.createTemplateFromFile("Index"); //"Index".html
  var check = html.evaluate();
  //  避免無法顯示在網際網路上
  var show = check.setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL);
  return show;

}



// 抓試算表裡的資料
function getData(){
        
  var ss=SpreadsheetApp.openById("1E34ECh1KXg5WOiDx4s9UInuJQ5PffTOLv9aQsS8qMUU");
 // 連結試算表
  var sheet=ss.getSheetByName("Sheet1");
  var data=sheet.getDataRange();

  return data.getValues();
}     

// 放資料進試算表裡


function doPost(e) {
  // 取得輸入參數
  let params = e.parameter; 
  let name = params.name;
  let mail = params.mail;
 
  // 初始化試算表
  let SpreadSheet = SpreadsheetApp.openById("1E34ECh1KXg5WOiDx4s9UInuJQ5PffTOLv9aQsS8qMUU");
  let Sheet = SpreadSheet.getSheetByName("Sheet1"); // 指定第一張試算表
  let LastRow = Sheet.getLastRow(); // 取得最後一列有值的索引值

  // 寫入試算表
  Sheet.getRange(LastRow+1, 1).setValue(name);
  Sheet.getRange(LastRow+1, 2).setValue(mail);
  
  if (method == "write") {
   write_data(para);
  }
  if (method == "read") {
  // 這裡放讀取資料的語法
  }

  // 回傳結果
  return ContentService
  .createTextOutput(JSON.stringify({ result: '成功', version: '1.0' }))
      .setMimeType(ContentService.MimeType.JSON); 




}

function write_data(para) {
  var number = para.number,
  date = para.date,
  name = para.name;
  sheet1.appendRow([number, date, name]); // 插入一列新的資料
}

/*
function test(){
var e = {
parameter:{
"method": "write",
"a": "hy00",
"b": "24164162",
"c": "lee"
}
}
doPost(e);
}
*/
