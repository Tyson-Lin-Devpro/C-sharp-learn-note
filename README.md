# C#學習歷程筆記

## 撰寫您的第一個 C# 程式碼

- 練習 - "Hello World!"
1. C#語言有大小寫之分  
2. 字串只能用雙引號包住 常值字串  
3. 語句結尾一定要加入分號，稱為 陳述式運算子的結尾   
4. Console.Write 之間使用逗號，稱為 成員存取運算子  
5. Console.Write與Console.WriteLine差別 : Console.Write可使用多組合併輸出成一行字串  
6. (1,2)xxxxx : 報錯訊息中的數字第一位是第幾行，第二位是指第幾個字元  
7. //兩條斜線是註解的寫法  

- 運作方式  
1. 什麼是編譯？ :  稱為 編譯器 的特殊程式，會將您的原始程式碼轉換成可由電腦 CPU 執行的不同格式。  
2. 什麼是語法？ : 程式設計語言的語法會包含關鍵字、運算子 (像是分號或括弧等特殊鍵盤字元)，以及編譯器強制執行的其他文法規則。  
3. 透過雙引號建立 常值字串  
4. WriteLine() 控制項組件稱為 方法
5. Console 控制項組件稱為 類別  

## 宣告和使用變數

### 變數名稱規則
- 變數是您儲存在電腦記憶體中的暫存值。
- 變數名稱只能包含英數字元與底線字元。 不允許井字號符號 # (也稱為數字符號或英鎊符號) 或貨幣符號 $ 之類的特殊字元。
- 變數名稱的開頭必須是字母或底線，而不是數字。
- 變數名稱 不得 為 C# 關鍵字。ex.decimal、string
- 變數名稱會區分大小寫。
### 宣告
  - 字串變數 : `string 變數名 = "任意字串";` ps.變數名是可以使用中文的  
  - 布林值 : `bool 變數名 = 布林值;`  
  - 透過+符號連結前後 
  ex. 
    ```
    string aFriend = "Tyson";
    Console.WriteLine("Hello" + aFriend); //輸出 Hello Tyson
    ```

  - 字串插補(String interpolation) :  
  ex.  
    ```
    string aFriend = "   Tyson   ";
    Console.WriteLine($"Hello {aFriend} 567"); //輸出 Hello Tyson
    ```
### 方法
  - 變數後可接屬性或方法 :  
    ```
    string aFriend = "   Tyson   ";
    ``` 
  - 字串長度 : `aFriend.Length //11   空格也列入計算`  
  - 去掉前後空白 : `aFriend.trim()`  
  - 去掉前面空白 : `aFriend.trimStart()`    
  - 去掉後面空白 : `aFriend.trimEnd()`  
  - 英文轉大寫 : `aFriend.ToUpper() //TYSON`  
  - 英文轉大寫 : `aFriend.ToLower() //tyson`  
    ```
    string abc = "Tyson  ";
    ``` 
  - 搜尋字詞 (ps.大小寫須完全一樣)   
  `abc.Contains("Ty") //True ` 
  `abc.Contains("tyson") //False `  
  - 搜尋字詞(由前向後匹配，空可也需匹配)  
  `abc.StartsWith("Tys"); //True`    
  `abc.StartsWith("Tysan"); //False`  
  - 搜尋字詞(由後向前匹配，空可也需匹配) :  
  `abc.EndsWith("on  "); //True`  
  `abc.EndsWith("son "); //False`  


## 在 C# 中操作整數和浮點數數字
### 宣告數字
- `int a = 50;`  
int 代表整數，包含正整數或負整數  
運算子 +加 -減 *乘 /除 %求餘數

- int 型別有最小和最大限制
  ```
  int max = int.MaxValue;
  int min = int.MinValue;
  Console.WriteLine($"The range of integers is {min} to {max}");
  //輸出 The range of integers is -2147483648 to 2147483647
  ```

- `double a = 50;`  
double 代表雙精確度浮點數，用於表示非常大或非常小的非整數單位  
double只能與同為double和int類型運算

- double 型別有最小和最大限制
  ```
  double max = double.MaxValue;
  double min = double.MinValue;
  Console.WriteLine($"The range of double is {min} to {max}");
  //輸出 The range of double is -1.79769313486232E+308 to 1.79769313486232E+308
  ```

- 使用 decimal 類型  
精確度比double高  
需在後方加上大寫字母M，否則，則會判定為double類型
  ```
  decimal c = 1.0M;
  decimal d = 3.0M;
  Console.WriteLine(c / d);
  ```
  #decimal只能與同為decimal和int類型運算

## 透過分支和迴圈陳述式了解條件式邏輯

- if 陳述式寫法
  ```
  if (a + b > 10)
      Console.WriteLine("");

  //or

  if ((a + b + c > 10) && (a == b))
  {
      Console.WriteLine("");
  }
  else
  {
      Console.WriteLine("");
  }
  ```

### 迴圈類型 :  
- while迴圈 寫法
  ```
  int counter = 0;
  while (counter < 10)
  {
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
  }
  ```
- do...while迴圈 寫法
  ```
  int counter = 0;
  do
  {
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
  } while (counter < 10);
  ```
- for迴圈 寫法
  ```
  for(int counter = 0; counter < 10; counter++)
  {
    Console.WriteLine($"Hello World! The counter is {counter}");
  }
  ```

- for嵌套迴圈 寫法
  ```
  for (int row = 1; row < 11; row++)
  {
    for (char column = 'a'; column < 'k'; column++)
    {
      Console.WriteLine($"The cell is ({row}, {column})");
    }
  }
  ```

## 了解如何使用一般清單類型管理資料收集

- 建立清單
  ```
  var names = new List<string> { "<name>", "Ana", "Felipe" };
  foreach (var name in names)
  {
    Console.WriteLine($"Hello {name.ToUpper()}!");
  }
  ```

- 增加清單內容  
`names.Add("XXX")`

- 刪除清單內容  
`names.Remove("XXX")`

- 查閱清單長度  
`names.Count`

- 搜尋清單內容  
`names.IndexOf("XXX") //回傳該字串的index，-1則表示查無資料`


- Sort方法會依標準順序排序清單中的所有專案(以字母順序排序字串)  
`names.Sort()`


## 使用 C# 邁出您的第一步

- 常值是絕對不會變更的硬式編碼值。
- 字元常值 使用單引號，且只能輸入一個字元。
  ```
  Console.WriteLine('b');
  //b
  Console.WriteLine('Hello World!');
  //錯誤
  //(1,19): error CS1012: Too many characters in character literal
  ```
- `m` 或稱為「常值尾碼」
  ```
  Console.WriteLine(12.3m);
  ```
## 隱含型別區域變數 ( Implicitly typed local variables )
- 使用var宣告:
  ```
  var message = "Hello world!";
  ```
- 首次宣告變數，會自動偵測變數值的型態，更改變數值時則無法改變其型態。
  ```
  var message = "Hello World!";
  message = 10.0m;

  //報誤訊息
  //(2,11): error CS0029: Cannot implicitly convert type 'decimal' to 'string'
  ```
- 變數必須初始化才能使用var關鍵字。
  ```
  var message;
  //報錯訊息
  //(1,5): error CS0818: Implicitly-typed variables must be initialized
  ```

## 字元逸出序列 ( Character Escape Sequences )
  - `\n` : 跳一行  
    `\t` : 空格
    ```
    Console.WriteLine("Hello\nWorld!");
    Console.WriteLine("Hello\tWorld!");
    //輸出
    //Hello
      World!
    //Hello   World!
    ```
  - `\\` : 反斜線
    ```
    Console.WriteLine("c:\\source\\repos");
    //輸出
    //c:\source\repos
    ```

## 逐字字串常值 ( Verbatim String Literal )
- 逐字字串常值將會保留所有空白與字元，您不需要逸出反斜線。
- 輸出格式、版面都會跟程式碼一樣。
- 使用 @ 指示詞 :
  ```
  Console.WriteLine(@"   c:\source\repos   
        (this is where your code goes)");
  //輸出
  //c:\source\repos   
      (this is where your code goes)
  ```

- 合併逐字常值與字串插補
  ```
  string projectName = "First-Project";
  Console.WriteLine($@"C:\Output\{projectName}\Data");
  //輸出
  //C:\Output\First-Project\Data
  ```

## 針對 C# 中的數字執行基本作業
- int 到 decimal 的資料類型轉換運算
  ```
  int first = 7;
  int second = 5;
  decimal quotient = (decimal)first / (decimal)second;
  Console.WriteLine(quotient);
  //輸出
  //1.4
  ```
- 運算順序
1. `P arentheses` (括弧) (必須先執行括弧內的內容)
2. `E xponents` (指數)
3. `M ultiplication` (乘法) 與 `D ivision` (除法) (由左至右)
4. `A ddition` (加法) 與 `S ubtraction` (減法) (由左至右)

- 「複合指派」運算子 ( Compound Assignment Operators )
1. '+=' : 目前值+指定值 ex. a=a+2 等同於 a+=2
2. '-=' : 目前值-指定值 ex. a=a-2 等同於 a-=2
3. '*=' : 目前值\*指定值 ex. a=a\*2 等同於 a\*=2 
4. '++' : 目前值+1
5. '--' : 目前值-1

- 在值之前或之後使用增量運算子
  ```
  int value = 1;
  value++;
  Console.WriteLine("First: " + value);
  Console.WriteLine("Second: " + value++); //此處會輸出舊值後才+1
  Console.WriteLine("Third: " + value);
  Console.WriteLine("Fourth: " + (++value));//此處會輸出+1後的值
  //輸出
  //First: 2
  //Second: 2
  //Third: 3
  //Fourth: 4
  ```