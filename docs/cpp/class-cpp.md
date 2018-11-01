---
title: class (C++)
ms.date: 11/04/2016
f1_keywords:
- class_cpp
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
ms.openlocfilehash: 4404767fc6cf07c2a7a23d460e13bb191fef387a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555143"
---
# <a name="class-c"></a>class (C++)

**クラス**キーワードはクラス型を宣言またはクラス型のオブジェクトを定義します。

## <a name="syntax"></a>構文

```
[template-spec]
class [ms-decl-spec] [tag [: base-list ]]
{
   member-list
} [declarators];
[ class ] tag declarators;
```

#### <a name="parameters"></a>パラメーター

*テンプレートの仕様*<br/>
テンプレートの指定 (省略可能)。 詳細についてを参照してください[テンプレート](templates-cpp.md)します。

*class*<br/>
**クラス**キーワード。

*ms 宣言の仕様*<br/>
ストレージ クラスの指定 (省略可能)。 詳細についてを参照してください、 [_ _declspec](../cpp/declspec.md)キーワード。

*タグ*<br/>
クラスに渡す型名。 タグは、クラスのスコープ内で予約語になります。 タグは省略できます。 省略した場合、匿名クラスが定義されます。 詳細については、次を参照してください。[匿名クラス型](../cpp/anonymous-class-types.md)します。

*基本リスト*<br/>
このクラスがメンバーを継承するクラスまたは構造体のリスト (省略可能)。 参照してください[基底クラスの](../cpp/base-classes.md)詳細についてはします。 各基本クラスまたは構造体名の前に、アクセス指定子 ([パブリック](../cpp/public-cpp.md)、[プライベート](../cpp/private-cpp.md)、[保護](../cpp/protected-cpp.md)) および[仮想](../cpp/virtual-cpp.md)キーワード。 メンバー アクセス テーブルを参照してください。[クラス メンバーへのアクセスの制御](member-access-control-cpp.md)詳細についてはします。

*メンバー リスト*<br/>
クラス メンバーのリスト。 参照してください[クラス メンバーの概要](../cpp/class-member-overview.md)詳細についてはします。

*宣言子*<br/>
クラス型の 1 つ以上のインスタンスの名前を指定する宣言子リスト。 クラスのすべてのデータ メンバーがある場合、宣言子は初期化子リストを含めることができます**パブリック**します。 これは、そのデータ メンバーは、構造の一般的な**パブリック**よりも、既定でクラス。 参照してください[概要の宣言子](../cpp/overview-of-declarators.md)詳細についてはします。

## <a name="remarks"></a>Remarks

一般的なクラスの詳細については、次のトピックのいずれかを参照してください。

- [struct](../cpp/struct-cpp.md)

- [union](../cpp/unions.md)

- [_ _multiple_inheritance](../cpp/inheritance-keywords.md)

- [_ _single_inheritance](../cpp/inheritance-keywords.md)

- [_ _virtual_inheritance](../cpp/inheritance-keywords.md)

マネージ クラスと構造体については、次を参照してください[クラスと構造体。](../windows/classes-and-structs-cpp-component-extensions.md)

## <a name="example"></a>例

```cpp
// class.cpp
// compile with: /EHsc
// Example of the class keyword
// Exhibits polymorphism/virtual functions.

#include <iostream>
#include <string>
#define TRUE = 1
using namespace std;

class dog
{
public:
   dog()
   {
      _legs = 4;
      _bark = true;
   }

   void setDogSize(string dogSize)
   {
      _dogSize = dogSize;
   }
   virtual void setEars(string type)      // virtual function
   {
      _earType = type;
   }

private:
   string _dogSize, _earType;
   int _legs;
   bool _bark;

};

class breed : public dog
{
public:
   breed( string color, string size)
   {
      _color = color;
      setDogSize(size);
   }

   string getColor()
   {
      return _color;
   }

   // virtual function redefined
   void setEars(string length, string type)
   {
      _earLength = length;
      _earType = type;
   }

protected:
   string _color, _earLength, _earType;
};

int main()
{
   dog mongrel;
   breed labrador("yellow", "large");
   mongrel.setEars("pointy");
   labrador.setEars("long", "floppy");
   cout << "Cody is a " << labrador.getColor() << " labrador" << endl;
}
```

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[クラスと構造体](../cpp/classes-and-structs-cpp.md)