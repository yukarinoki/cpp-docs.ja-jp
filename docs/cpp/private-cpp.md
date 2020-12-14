---
description: 詳細については、「private (C++)」を参照してください。
title: private (C++)
ms.date: 11/04/2016
f1_keywords:
- private_cpp
helpviewer_keywords:
- private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
ms.openlocfilehash: f9060dbbe32662a62fcda84b628877b52d87bdfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198623"
---
# <a name="private-c"></a>private (C++)

## <a name="syntax"></a>構文

```
private:
   [member-list]
private base-class
```

## <a name="remarks"></a>解説

クラスメンバーのリストの前にある場合、キーワードは、 **`private`** これらのメンバーがクラスのメンバー関数およびフレンドからのみアクセス可能であることを指定します。 これは、次のアクセス指定子またはクラスの末尾までで宣言されているすべてのメンバーに適用されます。

基底クラスの名前を前に付けた場合、キーワードは、 **`private`** 基底クラスのパブリックメンバーとプロテクトメンバーが派生クラスのプライベートメンバーであることを指定します。

クラスのメンバーの既定のアクセスはプライベートです。 構造体または共用体のメンバーの既定のアクセスはパブリックです。

基底クラスの既定のアクセスは、クラスの場合はプライベートで、構造体の場合はパブリックです。 共用体に基底クラスを設定することはできません。

関連情報については、「 [friend](../cpp/friend-cpp.md)」、「 [public](../cpp/public-cpp.md)」、「 [Protected](../cpp/protected-cpp.md)」、および「 [クラスメンバーへのアクセスの制御](member-access-control-cpp.md)」のメンバーアクセステーブルを参照してください。

## <a name="clr-specific"></a>/clr 固有

CLR 型では、C++ アクセス指定子キーワード ( **`public`** 、 **`private`** 、および) は、 **`protected`** アセンブリに関して型およびメソッドの可視性に影響を与える可能性があります。 詳細については、「 [メンバー Access Control](member-access-control-cpp.md)」を参照してください。

> [!NOTE]
> [/LN](../build/reference/ln-create-msil-module.md)でコンパイルされたファイルは、この動作の影響を受けません。 この場合、すべてのマネージド クラス (パブリックかプライベート) が表示されます。

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
[キーワード](../cpp/keywords-cpp.md)
