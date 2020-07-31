---
title: protected (C++)
ms.date: 11/04/2016
f1_keywords:
- protected_cpp
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
ms.openlocfilehash: 25b25447737a075bcf4f02f1c3049c996fb4c678
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227167"
---
# <a name="protected-c"></a>protected (C++)

## <a name="syntax"></a>構文

```
protected:
   [member-list]
protected base-class
```

## <a name="remarks"></a>解説

キーワードは、 **`protected`** 次のアクセス指定子 ( *member-list* **`public`** または **`private`** )、またはクラス定義の末尾まで、メンバーリスト内のクラスメンバーへのアクセスを指定します。 として宣言されたクラスメンバーは **`protected`** 、次の方法でのみ使用できます。

- これらのメンバーを最初に宣言したクラスのメンバー関数。

- これらのメンバーを最初に宣言したクラスのフレンド。

- これらのメンバーを最初に宣言したクラスからパブリックまたはプロテクトのアクセス レベルで派生したクラス。

- プロテクト メンバーへのプライベート アクセスもできる、プライベートとして設定した直接派生クラス。

基底クラスの名前を前に付けた場合、キーワードは、 **`protected`** 基底クラスのパブリックメンバーとプロテクトメンバーが派生クラスのプロテクトメンバーであることを指定します。

プロテクトメンバーは、メンバーとしてプライベートではなく **`private`** 、宣言されているクラスのメンバーだけがアクセスできますが、メンバーとしては公開されず、 **`public`** 任意の関数でアクセスできます。

としても宣言されているプロテクトメンバー **`static`** は、派生クラスのフレンド関数またはメンバー関数からアクセスできます。 として宣言されていないプロテクトメンバーは、派生クラス **`static`** へのポインター、参照、または派生クラスのオブジェクトによってのみ、派生クラスのフレンドおよびメンバー関数にアクセスできます。

関連情報については、「 [friend](../cpp/friend-cpp.md)」、「 [public](../cpp/public-cpp.md)」、「 [Private](../cpp/private-cpp.md)」、および「[クラスメンバーへのアクセスの制御](member-access-control-cpp.md)」のメンバーアクセステーブルを参照してください。

## <a name="clr-specific"></a>/clr 固有

CLR 型では、C++ アクセス指定子キーワード ( **`public`** 、 **`private`** 、および) は、 **`protected`** アセンブリに関して型およびメソッドの可視性に影響を与える可能性があります。 詳細については、「[メンバー Access Control](member-access-control-cpp.md)」を参照してください。

> [!NOTE]
> [/LN](../build/reference/ln-create-msil-module.md)でコンパイルされたファイルは、この動作の影響を受けません。 この場合、すべてのマネージド クラス (パブリックかプライベート) が表示されます。

## <a name="end-clr-specific"></a>END /clr 固有

## <a name="example"></a>例

```cpp
// keyword_protected.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class X {
public:
   void setProtMemb( int i ) { m_protMemb = i; }
   void Display() { cout << m_protMemb << endl; }
protected:
   int  m_protMemb;
   void Protfunc() { cout << "\nAccess allowed\n"; }
} x;

class Y : public X {
public:
   void useProtfunc() { Protfunc(); }
} y;

int main() {
   // x.m_protMemb;         error, m_protMemb is protected
   x.setProtMemb( 0 );   // OK, uses public access function
   x.Display();
   y.setProtMemb( 5 );   // OK, uses public access function
   y.Display();
   // x.Protfunc();         error, Protfunc() is protected
   y.useProtfunc();      // OK, uses public access function
                        // in derived class
}
```

## <a name="see-also"></a>関連項目

[クラス メンバーへのアクセス制御](member-access-control-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
