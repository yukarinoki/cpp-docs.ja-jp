---
title: public (C++)
ms.date: 11/04/2016
f1_keywords:
- public_cpp
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
ms.openlocfilehash: 24cc4dd3cd7e0c893664339e7ad83383839b0b11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600371"
---
# <a name="public-c"></a>public (C++)

## <a name="syntax"></a>構文

```
public:
   [member-list]
public base-class
```

## <a name="remarks"></a>Remarks

前に、クラス メンバーの一覧と、**パブリック**キーワードは、それらのメンバーが任意の関数からアクセスできることを指定します。 これは、次のアクセス指定子またはクラスの末尾までで宣言されているすべてのメンバーに適用されます。

基底クラスの名前、**パブリック**キーワードを指定、基底クラスのパブリックおよびプロテクト メンバーはパブリックとプロテクト メンバーはそれぞれ、派生クラスの。

クラスのメンバーの既定のアクセスはプライベートです。 構造体または共用体のメンバーの既定のアクセスはパブリックです。

基底クラスの既定のアクセスは、クラスの場合はプライベートで、構造体の場合はパブリックです。 共用体に基底クラスを設定することはできません。

詳細については、次を参照してください[プライベート](../cpp/private-cpp.md)、[保護](../cpp/protected-cpp.md)、[フレンド](../cpp/friend-cpp.md)、とでメンバー アクセス テーブル[クラス メンバーへのアクセスの制御](member-access-control-cpp.md).

## <a name="clr-specific"></a>/clr 固有

CLR 型では、C++ アクセス指定子のキーワード (**パブリック**、**プライベート**、および**保護**) 型およびアセンブリに関連メソッドの可視性に影響を与えることができます。 詳細については、次を参照してください。[メンバー アクセス コントロール](member-access-control-cpp.md)します。

> [!NOTE]
>  ファイルがコンパイルされた[/LN](../build/reference/ln-create-msil-module.md)この動作の影響は受けません。 この場合、すべてのマネージド クラス (パブリックかプライベート) が表示されます。

## <a name="end-clr-specific"></a>END /clr 固有

## <a name="example"></a>例

```cpp
// keyword_public.cpp
class BaseClass {
public:
   int pubFunc() { return 0; }
};

class DerivedClass : public BaseClass {};

int main() {
   BaseClass aBase;
   DerivedClass aDerived;
   aBase.pubFunc();       // pubFunc() is accessible
                          //    from any function
   aDerived.pubFunc();    // pubFunc() is still public in
                          //    derived class
}
```

## <a name="see-also"></a>関連項目

[クラス メンバーへのアクセス制御](member-access-control-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)