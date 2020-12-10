---
title: C++ プログラムの終了
description: C++ 言語プログラムを終了するための標準的な方法について説明します。
ms.date: 12/07/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.openlocfilehash: 15d31d8d454f6ac90e012d35ef14e6d6e0a9e29a
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933210"
---
# <a name="c-program-termination"></a>C++ プログラムの終了

C++ では、次の方法でプログラムを終了できます。

- 関数を呼び出し [`exit`](../c-runtime-library/reference/exit-exit-exit.md) ます。
- 関数を呼び出し [`abort`](../c-runtime-library/reference/abort.md) ます。
- [`return`](return-statement-cpp.md)からステートメントを実行 `main` します。

## <a name="exit-function"></a>`exit` 関数

で宣言された関数は、 [`exit`](../c-runtime-library/reference/exit-exit-exit.md) \<stdlib.h> C++ プログラムを終了します。 に引数として指定 `exit` された値は、プログラムのリターンコードまたは終了コードとしてオペレーティングシステムに返されます。 慣例により、ゼロのリターン コードは、プログラムが正常に完了したことを意味します。 で定義されている定数とを使用して、 `EXIT_FAILURE` `EXIT_SUCCESS` \<stdlib.h> プログラムの成功または失敗を示すことができます。

**`return`** 関数からステートメントを発行 `main` することは、 `exit` 戻り値を引数として関数を呼び出すことと同じです。

## <a name="abort-function"></a>`abort` 関数

関数は、 [`abort`](../c-runtime-library/reference/abort.md) 標準のインクルードファイルでも宣言されており、 \<stdlib.h> C++ プログラムを終了します。 との違い `exit` は、で `abort` は `exit` C++ ランタイム終了処理を実行できます (グローバルオブジェクトデストラクターは呼び出されます) が、 `abort` プログラムはすぐに終了します。 関数は、 `abort` 初期化されたグローバル静的オブジェクトの通常の破棄プロセスをバイパスします。 また、関数を使用して指定された特別な処理をバイパス [`atexit`](../c-runtime-library/reference/atexit.md) します。

## <a name="atexit-function"></a>`atexit` 関数

関数を使用して [`atexit`](../c-runtime-library/reference/atexit.md) 、プログラムが終了する前に実行するアクションを指定します。 の呼び出しの前に初期化されたグローバル静的オブジェクト `atexit` は、終了処理関数の実行前に破棄されませんでした。

## <a name="return-statement-in-main"></a>`return` ステートメント `main`

[`return`](return-statement-cpp.md)からステートメントを発行 `main` することは、関数の呼び出しと機能的には同じです `exit` 。 次の例を確認してください。

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

`exit`前の **`return`** 例のステートメントとステートメントは機能的には同じです。 通常、C++ では、以外の戻り値の型を持つ関数は **`void`** 値を返す必要があります。 `main`関数は例外であり、ステートメントなしで終了できます **`return`** 。 その場合は、呼び出しプロセスに実装固有の値を返します。 **`return`** ステートメントを使用すると、から戻り値を指定でき `main` ます。

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
   ShowData sd1( "CON" ), sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>関連項目

[`main` 関数とコマンドライン引数](main-function-command-line-args.md)
