---
title: C++ プログラムの終了
description: C++ 言語プログラムの方法について説明し exit ます。
ms.date: 01/15/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
no-loc:
- exit
- abort
- return
- main
- atexit
- void
ms.openlocfilehash: fd0c7699ae032b5551f4fbc37eb3b7fa999a168f
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352922"
---
# <a name="c-program-termination"></a>C++ プログラムの終了

C++ では、 exit 次の方法でプログラムを使用できます。

- 関数を呼び出し [exit](../c-runtime-library/reference/exit-exit-exit.md) ます。
- 関数を呼び出し [abort](../c-runtime-library/reference/abort.md) ます。
- [return](return-statement-cpp.md)からステートメントを実行 `main` します。

## <a name="no-locexit-function"></a>exit 関数

で宣言された関数は、 [exit](../c-runtime-library/reference/exit-exit-exit.md) \<stdlib.h> C++ プログラムを終了します。 の引数として指定 `exit` された値は、 return プログラムのコードまたはコードとしてオペレーティングシステムに渡され return exit ます。 慣例により、 return コードがゼロの場合は、プログラムが正常に完了したことを意味します。 で定義されている定数 EXIT_FAILURE と EXIT_SUCCESS を使用して、 \<stdlib.h> プログラムの成功または失敗を示すことができます。

**`return`** 関数からステートメントを発行 `main` することは、値を `exit` 引数として関数を呼び出すことと同じです return 。

## <a name="no-locabort-function"></a>abort 関数

関数は、 [abort](../c-runtime-library/reference/abort.md) 標準のインクルードファイルでも宣言されており、 \<stdlib.h> C++ プログラムを終了します。 との違いは、 `exit` `abort` `exit` C++ ランタイム終了処理を実行できることです (グローバルオブジェクトデストラクターは呼び出されます) が、では `abort` プログラムが直ちに終了します。 関数は、 `abort` 初期化されたグローバル静的オブジェクトの通常の破棄プロセスをバイパスします。 また、関数を使用して指定された特別な処理をバイパス [atexit](../c-runtime-library/reference/atexit.md) します。

## <a name="no-locatexit-function"></a>atexit 関数

関数を使用して、 [atexit](../c-runtime-library/reference/atexit.md) プログラムの終了前に実行するアクションを指定します。 の呼び出し前に初期化されたグローバルな静的オブジェクト **atexit** は、処理関数を実行する前に破棄されません exit 。

## <a name="no-locreturn-statement-in-no-locmain"></a>return ステートメント main

[return](return-statement-cpp.md)からステートメントを発行 `main` することは、関数の呼び出しと機能的には同じです `exit` 。 次に例を示します。

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

`exit`前の **`return`** 例のステートメントとステートメントは機能的には同じです。 ただし、C++ では、 return 値以外の型を持つ関数が必要です **`void`** return 。 ステートメントでは、 **`return`** return からの値を使用でき `main` ます。

## <a name="destruction-of-static-objects"></a>静的オブジェクトの破棄

`exit`からステートメントを呼び出したり、実行したりすると **`return`** `main` 、静的オブジェクトは初期化の逆の順序 (存在する場合はへの呼び出しの後) で破棄され `atexit` ます。 次の例は、こうした初期化やクリーンアップがどのように機能するのかを示します。

### <a name="example"></a>例

次の例で `sd1` は、にエントリする前に、静的オブジェクトと `sd2` が作成され、初期化されてい `main` ます。 このプログラムがステートメントを使用して終了する **`return`** と、最初に `sd2` が破棄されてから、が破棄され `sd1` ます。 `ShowData` クラスのデストラクターは、これらの静的オブジェクトに関連付けられたファイルを閉じます 

```cpp
// using_exit_or_return1.cpp
#include <stdio.h>
class ShowData {
public:
   // Constructor opens a file.
   ShowData( const char *szDev ) {
   errno_t err;
      err = fopen_s(&OutputDev, szDev, "w" );
   }

   // Destructor closes the file.
   ~ShowData() { fclose( OutputDev ); }

   // Disp function shows a string on the output device.
   void Disp( char *szData ) {
      fputs( szData, OutputDev );
   }
private:
   FILE *OutputDev;
};

//  Define a static object of type ShowData. The output device
//   selected is "CON" -- the standard output device.
ShowData sd1 = "CON";

//  Define another static object of type ShowData. The output
//   is directed to a file called "HELLO.DAT"
ShowData sd2 = "hello.dat";

int main() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

このコードを作成するもう 1 つの方法は、ブロック スコープを持つ `ShowData` オブジェクトを宣言して、スコープ外に出ると破棄できるようにすることです。

```cpp
int main() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>関連項目

[main 関数とコマンドライン引数](main-function-command-line-args.md)
