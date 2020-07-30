---
title: C++ プログラムの終了
description: 'C++ 言語プログラムの方法について説明し :::no-loc(exit)::: ます。'
ms.date: 01/15/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- :::no-loc(exit):::ing applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
no-loc:
- ':::no-loc(exit):::'
- ':::no-loc(abort):::'
- ':::no-loc(return):::'
- ':::no-loc(main):::'
- ':::no-loc(atexit):::'
- ':::no-loc(void):::'
ms.openlocfilehash: 216aef5dbe8d110f9d75d43b5009b89fc5bfda51
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227180"
---
# <a name="c-program-termination"></a>C++ プログラムの終了

C++ では、 :::no-loc(exit)::: 次の方法でプログラムを使用できます。

- 関数を呼び出し [:::no-loc(exit):::](:::no-loc(exit):::-function.md) ます。
- 関数を呼び出し [:::no-loc(abort):::](:::no-loc(abort):::-function.md) ます。
- [:::no-loc(return):::](:::no-loc(return):::-statement-cpp.md)からステートメントを実行 `:::no-loc(main):::` します。

## <a name="no-locexit-function"></a>:::no-loc(exit)::: 関数

で宣言された関数は、 [:::no-loc(exit):::](../c-runtime-library/reference/:::no-loc(exit):::-:::no-loc(exit):::-:::no-loc(exit):::.md) \<stdlib.h> C++ プログラムを終了します。 の引数として指定 `:::no-loc(exit):::` された値は、 :::no-loc(return)::: プログラムのコードまたはコードとしてオペレーティングシステムに渡され :::no-loc(return)::: :::no-loc(exit)::: ます。 慣例により、 :::no-loc(return)::: コードがゼロの場合は、プログラムが正常に完了したことを意味します。 で定義されている定数 EXIT_FAILURE と EXIT_SUCCESS を使用して、 \<stdlib.h> プログラムの成功または失敗を示すことができます。

**`:::no-loc(return):::`** 関数からステートメントを発行 `:::no-loc(main):::` することは、値を `:::no-loc(exit):::` 引数として関数を呼び出すことと同じです :::no-loc(return)::: 。

## <a name="no-locabort-function"></a>:::no-loc(abort)::: 関数

関数は、 [:::no-loc(abort):::](../c-runtime-library/reference/:::no-loc(abort):::.md) 標準のインクルードファイルでも宣言されており、 \<stdlib.h> C++ プログラムを終了します。 との違いは、 `:::no-loc(exit):::` `:::no-loc(abort):::` `:::no-loc(exit):::` C++ ランタイム終了処理を実行できることです (グローバルオブジェクトデストラクターは呼び出されます) が、では `:::no-loc(abort):::` プログラムが直ちに終了します。 関数は、 `:::no-loc(abort):::` 初期化されたグローバル静的オブジェクトの通常の破棄プロセスをバイパスします。 また、関数を使用して指定された特別な処理をバイパス [:::no-loc(atexit):::](../c-runtime-library/reference/:::no-loc(atexit):::.md) します。

## <a name="no-locatexit-function"></a>:::no-loc(atexit)::: 関数

関数を使用して、 [:::no-loc(atexit):::](../c-runtime-library/reference/:::no-loc(atexit):::.md) プログラムの終了前に実行するアクションを指定します。 の呼び出し前に初期化されたグローバルな静的オブジェクト **:::no-loc(atexit):::** は、処理関数を実行する前に破棄されません :::no-loc(exit)::: 。

## <a name="no-locreturn-statement-in-no-locmain"></a>:::no-loc(return):::ステートメント:::no-loc(main):::

[:::no-loc(return):::](:::no-loc(return):::-statement-cpp.md)からステートメントを発行 `:::no-loc(main):::` することは、関数の呼び出しと機能的には同じです `:::no-loc(exit):::` 。 次の例を確認してください。

```cpp
// :::no-loc(return):::_statement.cpp
#include <stdlib.h>
int :::no-loc(main):::()
{
    :::no-loc(exit):::( 3 );
    :::no-loc(return)::: 3;
}
```

`:::no-loc(exit):::`前の **`:::no-loc(return):::`** 例のステートメントとステートメントは機能的には同じです。 ただし、C++ では、 :::no-loc(return)::: 値以外の型を持つ関数が必要です **`:::no-loc(void):::`** :::no-loc(return)::: 。 ステートメントでは、 **`:::no-loc(return):::`** :::no-loc(return)::: からの値を使用でき `:::no-loc(main):::` ます。

## <a name="destruction-of-static-objects"></a>静的オブジェクトの破棄

`:::no-loc(exit):::`からステートメントを呼び出したり、実行したりすると **`:::no-loc(return):::`** `:::no-loc(main):::` 、静的オブジェクトは初期化の逆の順序 (存在する場合はへの呼び出しの後) で破棄され `:::no-loc(atexit):::` ます。 次の例は、こうした初期化やクリーンアップがどのように機能するのかを示します。

### <a name="example"></a>例

次の例で `sd1` は、にエントリする前に、静的オブジェクトと `sd2` が作成され、初期化されてい `:::no-loc(main):::` ます。 このプログラムがステートメントを使用して終了する **`:::no-loc(return):::`** と、最初に `sd2` が破棄されてから、が破棄され `sd1` ます。 `ShowData` クラスのデストラクターは、これらの静的オブジェクトに関連付けられたファイルを閉じます 

```cpp
// using_:::no-loc(exit):::_or_:::no-loc(return):::1.cpp
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
   :::no-loc(void)::: Disp( char *szData ) {
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

int :::no-loc(main):::() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

このコードを作成するもう 1 つの方法は、ブロック スコープを持つ `ShowData` オブジェクトを宣言して、スコープ外に出ると破棄できるようにすることです。

```cpp
int :::no-loc(main):::() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>関連項目

[:::no-loc(main):::関数とコマンドライン引数](:::no-loc(main):::-function-command-line-args.md)
