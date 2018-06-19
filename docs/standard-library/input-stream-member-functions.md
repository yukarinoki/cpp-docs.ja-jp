---
title: 入力ストリームのメンバー関数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input stream objects
- input streams, member functions
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41ab041fe3cee9a3b6065f22e5f96a44a56af030
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850041"
---
# <a name="input-stream-member-functions"></a>入力ストリームのメンバー関数

入力ストリームのメンバー関数は、ディスク入力に使用します。 次のようなメンバー関数があります。

- [入力ストリームの open 関数](#vclrftheopenfunctionforinputstreamsanchor11)

- [Get](#vclrfthegetfunctionanchor12)

- [Getline](#vclrfthegetlinefunctionanchor13)

- [読み取り](#vclrfthereadfunctionanchor14)

- [seekg 関数と tellg 関数](#vclrftheseekgandtellgfunctionsanchor7)

- [入力ストリームの close 関数](#vclrftheclosefunctionforinputstreamsanchor15)

## <a name="vclrftheopenfunctionforinputstreamsanchor11"></a>入力ストリームの open 関数

入力ファイル ストリーム (ifstream) を使用している場合は、そのストリームを特定のディスク ファイルに関連付ける必要があります。 これを行うには、コンストラクターで行うか、**open** 関数を使用することができます。 いずれの場合も、引数は同じです。

入力ストリームに関連付けられているファイルを開く場合、通常は [ios_base::openmode](../standard-library/ios-base-class.md#openmode) フラグを指定します (既定のモードは **ios::in** です)。 一覧については、 **open_mode**フラグを参照してください[開く](#vclrftheopenfunctionforinputstreamsanchor11)です。 フラグは、ビットごとの OR ( &#124; ) 演算子と組み合わせることができます。

ファイルを読み取るには、まず **fail** メンバー関数を使用して、そのファイルが存在するかどうかを調べます。

```cpp
istream ifile("FILENAME");

if (ifile.fail())
// The file does not exist ...
```

## <a name="vclrfthegetfunctionanchor12"></a> Get

書式設定されていない **get** メンバー関数は、**>>** 演算子のように機能しますが、例外が 2 つあります。 1 番目は、**get** 関数には余白が含まれますが、抽出では、**skipws** フラグが設定されている場合 (既定) に余白が除外される点です。 2 番目は、**get** 関数では、関連付けられた出力ストリーム (`cout` など) がフラッシュされる可能性が低い点です。

**get** 関数の一種は、バッファー アドレスと読み取る文字の最大数を指定します。 これは、次の例のように、特定の変数に送信される文字数を制限する場合に役立ちます。

```cpp
// ioo_get_function.cpp
// compile with: /EHsc
// Type up to 24 characters and a terminating character.
// Any remaining characters can be extracted later.
#include <iostream>
using namespace std;

int main()
{
   char line[25];
   cout << " Type a line terminated by carriage return\n>";
   cin.get( line, 25 );
   cout << line << endl;
}
```

### <a name="input"></a>入力

```Input
1234
```

### <a name="sample-output"></a>出力例

```Output
1234
```

## <a name="vclrfthegetlinefunctionanchor13"></a> Getline

**getline** メンバー関数は **get** 関数に似ています。 両方の関数で、入力の終端文字を指定する 3 番目の引数を使用できます。 既定値は改行文字です。 両方の関数は、必須の終端文字用に 1 つの文字を予約します。 ただし、**get** は終端文字をストリームに残し、**getline** は終端文字を削除します。

次の例では、入力ストリームの終端文字を指定します。

```cpp
// getline_func.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char line[100];
   cout << " Type a line terminated by 't'" << endl;
   cin.getline( line, 100, 't' );
   cout << line;
}
```

### <a name="input"></a>入力

```Input
test
```

## <a name="vclrfthereadfunctionanchor14"></a> 読み取り

**read** メンバー関数は、メモリの指定した領域に対するファイルからのバイト数を読み取ります。 length 引数は、読み取られるバイト数を決定します。 この引数を含めないと、ファイルの物理的な末尾に達した場合、またはテキストモードのファイルでは埋め込まれた `EOF` 文字が読み取られた場合に、読み取りが停止します。

この例では、給与ファイルからのバイナリ レコードを構造体に読み取ります。

```cpp
#include <fstream>
#include <iostream>
using namespace std;

int main()
{
   struct
   {
      double salary;
      char name[23];
   } employee;

   ifstream is( "payroll" );
   if( is ) {  // ios::operator void*()
      is.read( (char *) &employee, sizeof( employee ) );
      cout << employee.name << ' ' << employee.salary << endl;
   }
   else {
      cout << "ERROR: Cannot open file 'payroll'." << endl;
   }
}
```

プログラムでは、データ レコードが、構造体で指定されているとおりに、終端文字キャリッジ リターンや改行文字を含まずに正確に書式設定されていることが想定されます。

## <a name="vclrftheseekgandtellgfunctionsanchor7"></a>seekg 関数と tellg 関数

入力ファイル ストリームは、データを次に読み取るファイル内の位置を指す内部ポインターを保持します。 次に示すように、`seekg` 関数を使用してこのポインターを設定します。

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main( )
{
   char ch;

   ifstream tfile( "payroll" );
   if( tfile ) {
      tfile.seekg( 8 );        // Seek 8 bytes in (past salary)
      while ( tfile.good() ) { // EOF or failure stops the reading
         tfile.get( ch );
         if( !ch ) break;      // quit on null
         cout << ch;
      }
   }
   else {
      cout << "ERROR: Cannot open file 'payroll'." << endl;
   }
}
```

`seekg` を使用してレコード指向のデータ管理システムを実装するには、固定長のレコード サイズを、ファイルの末尾を基準にしたバイト位置を取得するレコード番号で乗算してから、**get** オブジェクトを使用してレコードを読み取ります。

`tellg` メンバー関数は、読み取るファイルの現在の位置を返します。 この値の型は `streampos` (\<iostream> で定義されている `typedef`) です。 次の例では、ファイルを読み取り、スペースの位置を示すメッセージを表示します。

```cpp
#include <fstream>
#include <iostream>
using namespace std;

int main( )
{
   char ch;
   ifstream tfile( "payroll" );
   if( tfile ) {
       while ( tfile.good( ) ) {
          streampos here = tfile.tellg();
          tfile.get( ch );
          if ( ch == ' ' )
             cout << "\nPosition " << here << " is a space";
       }
   }
   else {
      cout << "ERROR: Cannot open file 'payroll'." << endl;
   }
}
```

## <a name="vclrftheclosefunctionforinputstreamsanchor15"></a>入力ストリームの close 関数

**close** メンバー関数は、入力ファイル ストリームに関連付けられているディスク ファイルを閉じ、オペレーティング システム ファイル ハンドルを解放します。 [ifstream](../standard-library/basic-ifstream-class.md) デストラクターによってファイルが閉じられますが、同じストリーム オブジェクトの別のファイルを開く必要がある場合は **close** 関数を使用できます。

## <a name="see-also"></a>関連項目

[入力ストリーム](../standard-library/input-streams.md)<br/>
