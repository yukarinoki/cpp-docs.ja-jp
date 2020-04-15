---
title: public (C++)
ms.date: 11/04/2016
f1_keywords:
- public_cpp
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
ms.openlocfilehash: bf8293c6a6cf12154b02979de08035807991052c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376052"
---
# <a name="public-c"></a>public (C++)

## <a name="syntax"></a>構文

```
public:
   [member-list]
public base-class
```

## <a name="remarks"></a>解説

クラス メンバーのリストの前に **、public**キーワードは、これらのメンバーが任意の関数からアクセス可能であることを指定します。 これは、次のアクセス指定子またはクラスの末尾までで宣言されているすべてのメンバーに適用されます。

基本クラスの名前の前に public**キーワードを**付けると、基本クラスのパブリック メンバーとプロテクト メンバーがそれぞれ、派生クラスのパブリック メンバーとプロテクト メンバーであることを指定します。

クラスのメンバーの既定のアクセスはプライベートです。 構造体または共用体のメンバーの既定のアクセスはパブリックです。

基底クラスの既定のアクセスは、クラスの場合はプライベートで、構造体の場合はパブリックです。 共用体に基底クラスを設定することはできません。

詳細については、「[クラス メンバへのアクセスの制御](member-access-control-cpp.md)」の[「プライベート](../cpp/private-cpp.md)、[プロテクト](../cpp/protected-cpp.md)、[フレンド](../cpp/friend-cpp.md)、およびメンバ アクセスの表」を参照してください。

## <a name="clr-specific"></a>/clr 固有

CLR 型では、C++ アクセス指定子のキーワード (**パブリック**、**プライベート**、および**プロテクト**) は、アセンブリに関する型とメソッドの参照に影響を与える可能性があります。 詳細については、「メンバー[アクセス制御](member-access-control-cpp.md)」を参照してください。

> [!NOTE]
> [/LN](../build/reference/ln-create-msil-module.md)を指定してコンパイルされたファイルは、この動作の影響を受けません。 この場合、すべてのマネージド クラス (パブリックかプライベート) が表示されます。

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
[Keywords](../cpp/keywords-cpp.md)
