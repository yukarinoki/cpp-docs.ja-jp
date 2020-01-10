---
title: C++プログラムの終了
ms.date: 12/10/2019
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
ms.openlocfilehash: a0e86cacd951327d39296a183be5ee4fbc36fd15
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301341"
---
# <a name="c-program-termination"></a>C++プログラムの終了

でC++は、次の方法でプログラムを終了できます。

- [Exit](exit-function.md)関数を呼び出します。
- [Abort](abort-function.md)関数を呼び出します。
- `main`から[return](return-statement-cpp.md)ステートメントを実行します。

## <a name="exit-function"></a>exit 関数

\<stdlib.h> > で宣言されている[exit](../c-runtime-library/reference/exit-exit-exit.md)関数は、プログラムC++を終了します。 `exit` の引数として指定された値は、プログラムのリターンコードまたは終了コードとしてオペレーティングシステムに返されます。 慣例により、ゼロのリターン コードは、プログラムが正常に完了したことを意味します。 \<stdlib.h> > で定義されている定数 EXIT_FAILURE と EXIT_SUCCESS を使用して、プログラムの成功または失敗を示すことができます。

`main` 関数から**return**ステートメントを発行することは、戻り値を引数として `exit` 関数を呼び出すことと同じです。

## <a name="abort-function"></a>abort 関数

[abort](../c-runtime-library/reference/abort.md) 関数（標準インクルードファイル \<stdlib.h> で宣言されている）はC++プログラムを終了させます。 `exit` と `abort` の違いは、`exit` によってC++実行時の終了処理を実行できることです (グローバルオブジェクトのデストラクターが呼び出されます)。一方、`abort` はプログラムをすぐに終了します。 `abort` 関数は、初期化されたグローバル静的オブジェクトの通常の破棄プロセスをバイパスします。 また、 [atexit](../c-runtime-library/reference/atexit.md)関数を使用して指定された特別な処理も省略します。

## <a name="atexit-function"></a>atexit 関数

[Atexit](../c-runtime-library/reference/atexit.md)関数を使用して、プログラムの終了前に実行するアクションを指定します。 **Atexit**の呼び出し前に初期化されたグローバルな静的オブジェクトは、終了処理関数を実行する前に破棄されます。

## <a name="return-statement-in-main"></a>main の return ステートメント

発行、[return](return-statement-cpp.md)ステートメントから`main`呼び出しと同じ機能が、`exit`関数。 次に例を示します。

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

`exit`と**return**前の例のステートメントは機能的に同じです。 ただし、 C++では、 **void**以外の戻り値の型を持つ関数は値を返す必要があります。 **return**ステートメントを使用するから値を返す`main`します。

## <a name="destruction-of-static-objects"></a>静的オブジェクトの破棄

`exit` を呼び出したとき、または `main`から**return**ステートメントを実行すると、静的オブジェクトは初期化の逆の順序 (存在する場合は `atexit` の呼び出しの後) で破棄されます。 次の例は、こうした初期化やクリーンアップがどのように機能するのかを示します。

### <a name="example"></a>使用例

次の例では、`main`に入る前に、静的オブジェクト `sd1` および `sd2` が作成され、初期化されます。 使用してこのプログラムの終了後、**return**ステートメントでは、まず`sd2`が破棄されるし、 `sd1`。 `ShowData` クラスのデストラクターは、これらの静的オブジェクトに関連付けられたファイルを閉じます

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

[main: プログラムの起動](main-program-startup.md)