---
title: class (C++)
ms.date: 11/04/2016
f1_keywords:
- class_cpp
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
ms.openlocfilehash: c1b9d8f6510dfe15644f0e47cad7e0aecbac36c9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180977"
---
# <a name="class-c"></a>class (C++)

Class**キーワードは**、クラス型を宣言するか、クラス型のオブジェクトを定義します。

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

*テンプレート-仕様*<br/>
テンプレートの指定 (省略可能)。 詳細については、「[テンプレート](templates-cpp.md)」を参照してください。

*class*<br/>
**Class**キーワード。

*ms の宣言*<br/>
ストレージ クラスの指定 (省略可能)。 詳細については、 [__declspec](../cpp/declspec.md)キーワードを参照してください。

*番号*<br/>
クラスに渡す型名。 タグは、クラスのスコープ内で予約語になります。 タグは省略できます。 省略した場合、匿名クラスが定義されます。 詳細については、「[匿名クラス型](../cpp/anonymous-class-types.md)」を参照してください。

*base-list*<br/>
このクラスがメンバーを継承するクラスまたは構造体のリスト (省略可能)。 詳細については、「[基底クラス](../cpp/base-classes.md)」を参照してください。 各基底クラスまたは構造体の名前の前には、アクセス指定子 ([public](../cpp/public-cpp.md)、 [private](../cpp/private-cpp.md)、 [protected](../cpp/protected-cpp.md)) と[virtual](../cpp/virtual-cpp.md)キーワードを付けることができます。 詳細については、「[クラスメンバーへのアクセスの制御](member-access-control-cpp.md)」のメンバーアクセステーブルを参照してください。

*メンバーリスト*<br/>
クラス メンバーのリスト。 詳細については、[クラスメンバーの概要](../cpp/class-member-overview.md)に関するトピックを参照してください。

*declarators*<br/>
クラス型の 1 つ以上のインスタンスの名前を指定する宣言子リスト。 クラスのすべてのデータメンバーが**パブリック**である場合は、宣言子に初期化子リストを含めることができます。 これは、クラスよりもデータメンバーが既定で**パブリック**である構造体では一般的です。 詳細については、「[宣言子の概要](../cpp/overview-of-declarators.md)」を参照してください。

## <a name="remarks"></a>解説

一般的なクラスの詳細については、次のトピックのいずれかを参照してください。

- [struct](../cpp/struct-cpp.md)

- [union](../cpp/unions.md)

- [__multiple_inheritance](../cpp/inheritance-keywords.md)

- [__single_inheritance](../cpp/inheritance-keywords.md)

- [__virtual_inheritance](../cpp/inheritance-keywords.md)

/Cli およびC++ C++/cx のマネージクラスと構造体の詳細については、「[クラスと構造体](../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください。

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

## <a name="see-also"></a>参照

[キーワード](../cpp/keywords-cpp.md)<br/>
[クラスと構造体](../cpp/classes-and-structs-cpp.md)
