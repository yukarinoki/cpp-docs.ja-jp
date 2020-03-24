---
title: protected (C++)
ms.date: 11/04/2016
f1_keywords:
- protected_cpp
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
ms.openlocfilehash: 29f57eac7201ac0647275c70c539f9b2f28eb81b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179251"
---
# <a name="protected-c"></a>protected (C++)

## <a name="syntax"></a>構文

```
protected:
   [member-list]
protected base-class
```

## <a name="remarks"></a>解説

**Protected**キーワードは、次のアクセス指定子 (**パブリック**または**プライベート**) またはクラス定義の末尾まで、*メンバーリスト*内のクラスメンバーへのアクセスを指定します。 Protected として宣言され**た**クラスメンバーは、次の方法でのみ使用できます。

- これらのメンバーを最初に宣言したクラスのメンバー関数。

- これらのメンバーを最初に宣言したクラスのフレンド。

- これらのメンバーを最初に宣言したクラスからパブリックまたはプロテクトのアクセス レベルで派生したクラス。

- プロテクト メンバーへのプライベート アクセスもできる、プライベートとして設定した直接派生クラス。

基底クラスの名前の前にある場合、 **protected**キーワードは、基底クラスのパブリックメンバーとプロテクトメンバーが派生クラスのプロテクトメンバーであることを指定します。

プロテクトメンバーは**プライベート**メンバーとしてプライベートではなく、宣言されているクラスのメンバーだけがアクセスできますが **、パブリックメンバーとし**ては公開されず、任意の関数でアクセスできます。

**静的**としても宣言されているプロテクトメンバーには、派生クラスの任意のフレンド関数またはメンバー関数からアクセスできます。 **静的**として宣言されていないプロテクトメンバーは、派生クラスへのポインター、参照、または派生クラスのオブジェクトによってのみ、派生クラスのフレンドおよびメンバー関数にアクセスできます。

関連情報については、「 [friend](../cpp/friend-cpp.md)」、「 [public](../cpp/public-cpp.md)」、「 [Private](../cpp/private-cpp.md)」、および「[クラスメンバーへのアクセスの制御](member-access-control-cpp.md)」のメンバーアクセステーブルを参照してください。

## <a name="clr-specific"></a>/clr 固有

CLR 型では、 C++アクセス指定子キーワード (**public**、 **private**、 **protected**) は、アセンブリに関して型およびメソッドの可視性に影響を与える可能性があります。 詳細については、「[メンバー Access Control](member-access-control-cpp.md)」を参照してください。

> [!NOTE]
>  [/LN](../build/reference/ln-create-msil-module.md)でコンパイルされたファイルは、この動作の影響を受けません。 この場合、すべてのマネージド クラス (パブリックかプライベート) が表示されます。

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

## <a name="see-also"></a>参照

[クラス メンバーへのアクセス制御](member-access-control-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
