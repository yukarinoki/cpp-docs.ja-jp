---
description: 詳細については、「コンパイラエラー C3861」を参照してください。
title: コンパイラ エラー C3861
ms.date: 03/23/2018
f1_keywords:
- C3861
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
ms.openlocfilehash: bba259496de09e86b59f9cad1ac1bf89a697a1da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222906"
---
# <a name="compiler-error-c3861"></a>コンパイラ エラー C3861

> '*identifier*': 識別子が見つかりません

コンパイラでは、引数依存の検索を使用しても、識別子への参照を解決できませんでした。

## <a name="remarks"></a>解説

このエラーを修正するには、 *識別子と* 大文字/小文字の識別子の宣言を比較します。 [スコープ解決演算子](../../cpp/scope-resolution-operator.md)と名前空間の[using ディレクティブ](../../cpp/namespaces-cpp.md#using_directives)が正しく使用されていることを確認します。 識別子がヘッダーファイルで宣言されている場合は、識別子が参照される前にヘッダーが含まれていることを確認します。 識別子が外部から参照可能である場合は、それを使用するソースファイルで宣言されていることを確認します。 また、識別子の宣言または定義が [条件付きコンパイルディレクティブ](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)によって除外されていないことを確認します。

Visual Studio 2015 の C ランタイムライブラリから古い関数を削除するように変更すると、C3861 が発生する可能性があります。 このエラーを解決するには、これらの関数への参照を削除するか、セキュリティで保護された代替手段 (存在する場合) に置き換えます。 詳細については、「廃止された [関数](../../c-runtime-library/obsolete-functions.md)」を参照してください。

以前のバージョンのコンパイラからプロジェクトを移行した後にエラー C3861 が表示される場合は、サポートされている Windows バージョンに関連する問題が発生する可能性があります。 Visual C++ では、Windows 95、Windows 98、Windows ME、Windows NT、および Windows 2000 がサポート対象外になりました。 **WINVER** マクロまたは **_WIN32_WINNT** マクロをこれらのいずれかのバージョンの Windows に割り当てている場合は、そのマクロを修正する必要があります。 詳細については、「 [WINVER と _WIN32_WINNT の変更](../../porting/modifying-winver-and-win32-winnt.md)」を参照してください。

## <a name="examples"></a>例

### <a name="undefined-identifier"></a>未定義の識別子です。

次の例では、識別子が定義されていないため、C3861 が生成されます。

```cpp
// C3861.cpp
void f2(){}
int main() {
   f();    // C3861
   f2();   // OK
}
```

### <a name="identifier-not-in-scope"></a>識別子がスコープ内にありません

次の例では、識別子は、それを使用する他のソースファイルで宣言されていない限り、定義のファイルスコープでのみ表示されるため、C3861 が生成されます。

```cpp
// C3861_a1.cpp
// Compile with: cl /EHsc /W4 C3861_a1.cpp C3861_a2.cpp
#include <iostream>
// Uncomment the following line to fix:
// int f();  // declaration makes external function visible
int main() {
   std::cout << f() << std::endl;    // C3861
}
```

```cpp
// C3861_a2.cpp
int f() {  // declared and defined here
   return 42;
}
```

### <a name="namespace-qualification-required"></a>名前空間の修飾が必要です

C++ 標準ライブラリの例外クラスには、 `std` 名前空間が必要です。

```cpp
// C3861_b.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   try {
      throw exception("Exception");   // C3861
      // try the following line instead
      // throw std::exception("Exception");
   }
   catch (...) {
      std::cout << "caught an exception" << std::endl;
   }
}
```

### <a name="obsolete-function-called"></a>互換性のために残された関数

廃止された関数は、CRT ライブラリから削除されました。

```cpp
// C3861_c.cpp
#include <stdio.h>
int main() {
   char line[21]; // room for 20 chars + '\0'
   gets( line );  // C3861
   // Use gets_s instead.
   printf( "The line entered was: %s\n", line );
}
```

### <a name="adl-and-friend-functions"></a>ADL 関数と friend 関数

次の例では、コンパイラはに対して引数依存の参照を使用できないため、C3767 が生成され `FriendFunc` ます。

```cpp
namespace N {
   class C {
      friend void FriendFunc() {}
      friend void AnotherFriendFunc(C* c) {}
   };
}

int main() {
   using namespace N;
   FriendFunc();   // C3861 error
   C* pC = new C();
   AnotherFriendFunc(pC);   // found via argument-dependent lookup
}
```

このエラーを解決するには、クラススコープでフレンドを宣言し、名前空間スコープで定義します。

```cpp
class MyClass {
   int m_private;
   friend void func();
};

void func() {
   MyClass s;
   s.m_private = 0;
}

int main() {
   func();
}
```
