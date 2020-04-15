---
title: private (C++)
ms.date: 11/04/2016
f1_keywords:
- private_cpp
helpviewer_keywords:
- private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
ms.openlocfilehash: d6dc1ca309c096a4f5e857ade3d7550749991f3f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366207"
---
# <a name="private-c"></a>private (C++)

## <a name="syntax"></a>構文

```
private:
   [member-list]
private base-class
```

## <a name="remarks"></a>解説

クラス メンバーのリストの前に **、private**キーワードは、メンバー関数とクラスのフレンドからのみそれらのメンバーにアクセスできるように指定します。 これは、次のアクセス指定子またはクラスの末尾までで宣言されているすべてのメンバーに適用されます。

基本クラスの名前の前に **、private**キーワードは、基本クラスのパブリック メンバーとプロテクト メンバーが派生クラスのプライベート メンバーであることを指定します。

クラスのメンバーの既定のアクセスはプライベートです。 構造体または共用体のメンバーの既定のアクセスはパブリックです。

基底クラスの既定のアクセスは、クラスの場合はプライベートで、構造体の場合はパブリックです。 共用体に基底クラスを設定することはできません。

関連情報については、「[フレンド](../cpp/friend-cpp.md)、[パブリック](../cpp/public-cpp.md)、[プロテ](../cpp/protected-cpp.md)クト」、および[「クラス メンバーへのアクセスの制御](member-access-control-cpp.md)」の「メンバーアクセス」の表を参照してください。

## <a name="clr-specific"></a>/clr 固有

CLR 型では、C++ アクセス指定子のキーワード (**パブリック**、**プライベート**、および**プロテクト**) は、アセンブリに関する型とメソッドの参照に影響を与える可能性があります。 詳細については、「メンバー[アクセス制御](member-access-control-cpp.md)」を参照してください。

> [!NOTE]
> [/LN](../build/reference/ln-create-msil-module.md)を指定してコンパイルされたファイルは、この動作の影響を受けません。 この場合、すべてのマネージド クラス (パブリックかプライベート) が表示されます。

## <a name="end-clr-specific"></a>END /clr 固有

## <a name="example"></a>例

```cpp
// keyword_private.cpp
class BaseClass {
public:
   // privMem accessible from member function
   int pubFunc() { return privMem; }
private:
   void privMem;
};

class DerivedClass : public BaseClass {
public:
   void usePrivate( int i )
      { privMem = i; }   // C2248: privMem not accessible
                         // from derived class
};

class DerivedClass2 : private BaseClass {
public:
   // pubFunc() accessible from derived class
   int usePublic() { return pubFunc(); }
};

int main() {
   BaseClass aBase;
   DerivedClass aDerived;
   DerivedClass2 aDerived2;
   aBase.privMem = 1;     // C2248: privMem not accessible
   aDerived.privMem = 1;  // C2248: privMem not accessible
                          //    in derived class
   aDerived2.pubFunc();   // C2247: pubFunc() is private in
                          //    derived class
}
```

## <a name="see-also"></a>関連項目

[クラス メンバーへのアクセス制御](member-access-control-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)
