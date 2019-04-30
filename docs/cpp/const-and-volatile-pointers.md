---
title: const ポインターと volatile ポインター
ms.date: 11/04/2016
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
ms.openlocfilehash: c869adbbdc8a5a17d315e64e5ac15545e0c46e26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399123"
---
# <a name="const-and-volatile-pointers"></a>const ポインターと volatile ポインター

[Const](../cpp/const-cpp.md)と[揮発性](../cpp/volatile-cpp.md)キーワードは、ポインターの処理方法を変更します。 **Const**キーワードでは、初期化後に、ポインターを変更できないことを指定します。 ポインターがその後、変更から保護します。

**揮発性**キーワードは、ユーザー アプリケーション以外の操作によってに続く名前に関連付けられている値を変更できることを指定します。 そのため、**揮発性**キーワードは複数のプロセスや割り込みサービス ルーチンとの通信に使用するグローバル データ領域からアクセスできる共有メモリでオブジェクトを宣言するのに便利です。

名前として宣言されている場合**揮発性**コンパイラがメモリから値をプログラムによりアクセスされるたびに再読み込みします。 これによって、可能な最適化が大幅に減少します。 ただし、オブジェクトの状態が予期せず変わる場合、これが予測可能なプログラムの実行を保証する唯一の方法になります。

としてポインターが指すオブジェクトを宣言する**const**または**揮発性**形式の宣言を使用します。

```cpp
const char *cpch;
volatile char *vpch;
```

ポインターの値を宣言する — ポインターに格納されている実際のアドレスは、-として**const**または**揮発性**形式の宣言を使用します。

```cpp
char * const pchc;
char * volatile pchv;
```

C++ 言語は、オブジェクトを変更できるようにするための割り当てを禁止またはとして宣言されたポインター **const**します。 このような代入を実行すると、オブジェクトまたはポインターを宣言したときの情報が削除されるため、元の宣言の意図に反することになります。 次に宣言の例を示します。

```cpp
const char cch = 'A';
char ch = 'B';
```

2 つのオブジェクトの前に宣言した (`cch`、型の**const char**、および`ch`、型の**char)**、次の宣言と初期化が無効です。

```cpp
const char *pch1 = &cch;
const char *const pch4 = &cch;
const char *pch5 = &ch;
char *pch6 = &ch;
char *const pch7 = &ch;
const char *const pch8 = &ch;
```

次の宣言と初期化はエラーになります。

```cpp
char *pch2 = &cch;   // Error
char *const pch3 = &cch;   // Error
```

`pch2` の宣言は、定数オブジェクトを変更する可能性があるポインターを宣言するため、許可されません。 宣言`pch3`、定数のポインターを指定します; オブジェクトではなく、宣言が同じ理由で許可されていない、`pch2`宣言は許可されません。

次の 8 つの代入は、ポインターを介した代入と、前に宣言したポインター値の変更を示しています。ここでは、初期化が `pch1` から `pch8` まで正しかったと仮定します。

```cpp
*pch1 = 'A';  // Error: object declared const
pch1 = &ch;   // OK: pointer not declared const
*pch2 = 'A';  // OK: normal pointer
pch2 = &ch;   // OK: normal pointer
*pch3 = 'A';  // OK: object not declared const
pch3 = &ch;   // Error: pointer declared const
*pch4 = 'A';  // Error: object declared const
pch4 = &ch;   // Error: pointer declared const
```

として宣言されたポインター**揮発性**、またはの組み合わせとして**const**と**揮発性**、同じ規則に従います。

ポインター **const**オブジェクトは次のように関数宣言で使用多くの場合。

```cpp
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );
```

前のステートメントは、関数を宣言[strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)へのポインター型の 3 つの引数の 2 つが、 **char**します。 引数が参照によって渡されますないため、値によって、関数は両方を変更する無料`strDestination`と`strSource`場合`strSource`として宣言されていない**const**します。 宣言`strSource`として**const**により、呼び出し元`strSource`呼び出された関数では変更できません。

> [!NOTE]
> 標準変換があるため、 *typename* <strong>\*</strong>に**const** *typename*  <strong>\*</strong>、型の引数を渡すことは`char *`に[strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)します。 ただし、その逆は正しくありません。削除する暗黙的な変換が存在しない、 **const**オブジェクトまたはポインターからの属性。

A **const**指定された型のポインターは、同じ型のポインターに割り当てることができます。 ただし、ポインターでない**const**に割り当てることはできません、 **const**ポインター。 次のコードは、正しい代入と正しくない代入を示します。

```cpp
// const_pointer.cpp
int *const cpObject = 0;
int *pObject;

int main() {
pObject = cpObject;
cpObject = pObject;   // C3892
}
```

次のサンプルは、オブジェクトへのポインターへのポインターがあるとき、オブジェクトを定数として宣言する方法を示します。

```cpp
// const_pointer2.cpp
struct X {
   X(int i) : m_i(i) { }
   int m_i;
};

int main() {
   // correct
   const X cx(10);
   const X * pcx = &cx;
   const X ** ppcx = &pcx;

   // also correct
   X const cx2(20);
   X const * pcx2 = &cx2;
   X const ** ppcx2 = &pcx2;
}
```

## <a name="see-also"></a>関連項目

[ポインター](../cpp/pointers-cpp.md)