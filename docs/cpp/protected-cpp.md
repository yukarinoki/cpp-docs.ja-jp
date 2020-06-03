---
title: protected (C++)
ms.date: 11/04/2016
f1_keywords:
- protected_cpp
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
ms.openlocfilehash: 79ca081726c1f26a251763e2533ade730f075e2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317266"
---
# <a name="protected-c"></a>protected (C++)

## <a name="syntax"></a>構文

```
protected:
   [member-list]
protected base-class
```

## <a name="remarks"></a>解説

**protected**キーワードは *、次*のアクセス指定子 (**public**または**private**) またはクラス定義の最後までのメンバー リスト内のクラス メンバーへのアクセスを指定します。 **protected**として宣言されたクラス メンバーは、次の場合にのみ使用できます。

- これらのメンバーを最初に宣言したクラスのメンバー関数。

- これらのメンバーを最初に宣言したクラスのフレンド。

- これらのメンバーを最初に宣言したクラスからパブリックまたはプロテクトのアクセス レベルで派生したクラス。

- プロテクト メンバーへのプライベート アクセスもできる、プライベートとして設定した直接派生クラス。

基本クラスの名前の前に **、protected**キーワードは、基本クラスのパブリック メンバーとプロテクト メンバーがその派生クラスのプロテクト メンバーであることを指定します。

プロテクト メンバーは**プライベート**メンバーほどプライベートではなく、宣言されているクラスのメンバーだけがアクセスできますが、パブリック メンバーほど**パブリック**ではありません。

**静的**として宣言されたプロテクト メンバーは、派生クラスのフレンド関数またはメンバー関数からもアクセスできます。 **静的**として宣言されていないプロテクト メンバーは、派生クラスのポインター、参照、またはオブジェクトを介してのみ、派生クラス内のフレンドおよびメンバー関数からアクセスできます。

関連情報については、「[クラス メンバへのアクセスの制御](member-access-control-cpp.md)」の[フレンド](../cpp/friend-cpp.md)、[パブリック](../cpp/public-cpp.md)、[プライベート](../cpp/private-cpp.md)、およびメンバ アクセスの各表を参照してください。

## <a name="clr-specific"></a>/clr 固有

CLR 型では、C++ アクセス指定子のキーワード (**パブリック**、**プライベート**、および**プロテクト**) は、アセンブリに関する型とメソッドの参照に影響を与える可能性があります。 詳細については、「メンバー[アクセス制御](member-access-control-cpp.md)」を参照してください。

> [!NOTE]
> [/LN](../build/reference/ln-create-msil-module.md)を指定してコンパイルされたファイルは、この動作の影響を受けません。 この場合、すべてのマネージド クラス (パブリックかプライベート) が表示されます。

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
[Keywords](../cpp/keywords-cpp.md)
