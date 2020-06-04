---
title: code_seg (__declspec)
ms.date: 11/04/2016
f1_keywords:
- code_seg_cpp
helpviewer_keywords:
- code_seg __declspec keyword
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
ms.openlocfilehash: 22703e92b1a127378c965ce12bcc4e5475b3e452
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180837"
---
# <a name="code_seg-__declspec"></a>code_seg (__declspec)

**Microsoft 固有の仕様**

**Code_seg**宣言属性は、関数またはクラスメンバー関数のオブジェクトコードが格納される .obj ファイル内の実行可能なテキストセグメントに名前を指定します。

## <a name="syntax"></a>構文

```
__declspec(code_seg("segname")) declarator
```

## <a name="remarks"></a>解説

`__declspec(code_seg(...))` 属性では、メモリ内でそれぞれページングまたはロックできる個別の名前のセグメントにコードを格納できます。 この属性を使用して、インスタンス化されたテンプレートとコンパイラによって生成されたコードの格納場所を制御できます。

*セグメント*は、1つの単位としてメモリに読み込まれる .obj ファイル内のデータの名前付きブロックです。 *テキストセグメント*は、実行可能コードを含むセグメントです。 Term*セクション*は、多くの場合、セグメントと同じ意味で使用されます。

`declarator` が定義されているときに生成されるオブジェクト コードは、ナロー文字列リテラルである `segname` で指定されたテキスト セグメントに格納されます。 `segname` 名前は、宣言で使用する前に[section](../preprocessor/section.md)プラグマで指定する必要はありません。 既定では、`code_seg` が指定されていないと、オブジェクト コードは .text という名前のセグメントに格納されます。 **Code_seg**属性は、既存の[#pragma code_seg](../preprocessor/code-seg.md)ディレクティブよりも優先されます。 メンバー関数に適用された**code_seg**属性は、外側のクラスに適用されているすべての**code_seg**属性よりも優先されます。

エンティティに**code_seg**属性がある場合は、同じエンティティのすべての宣言と定義が同じ**code_seg**属性を持つ必要があります。 基底クラスに**code_seg**属性がある場合、派生クラスは同じ属性を持つ必要があります。

名前空間スコープ関数またはメンバー関数に**code_seg**属性が適用されると、その関数のオブジェクトコードが指定されたテキストセグメントに格納されます。 この属性がクラスに適用されると、そのクラスおよび入れ子にされたクラスのメンバー関数はすべて (コンパイラによって生成された特殊なメンバー関数も含めて)、指定されたセグメントに格納されます。 ローカルに定義されたクラス (メンバー関数本体で定義されたクラスなど) は、外側のスコープの**code_seg**属性を継承しません。

**Code_seg**属性がテンプレートクラスまたはテンプレート関数に適用されると、テンプレートのすべての暗黙的な特殊化が指定されたセグメントに格納されます。 明示的または部分的な特殊化は、プライマリテンプレートから**code_seg**属性を継承しません。 特殊化で同じまたは別の**code_seg**属性を指定することもできます。 **Code_seg**属性は、明示的なテンプレートのインスタンス化には適用できません。

既定では、コンパイラによって生成されたコード (特殊なメンバー関数など) は .text セグメントに格納されます。 `#pragma code_seg` ディレクティブは、この既定をオーバーライドしません。 クラス、クラステンプレート、または関数テンプレートの**code_seg**属性を使用して、コンパイラによって生成されるコードが配置される場所を制御します。

ラムダは、外側のスコープから**code_seg**属性を継承します。 ラムダのセグメントを指定するには、パラメーター宣言句の後、変更可能なまたは例外の指定、後続の戻り値の型の指定、およびラムダの本体の前に、 **code_seg**属性を適用します。 詳細については、「[ラムダ式の構文](../cpp/lambda-expression-syntax.md)」を参照してください。 この例では、ラムダを PagedMem という名前のセグメントに定義しています。

```cpp
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };
```

特定のメンバー関数 (特に仮想メンバー関数) を異なるセグメントに格納するときには注意が必要です。 ページング セグメントに存在する派生クラスの仮想関数を定義する場合、基底クラスのメソッドが非ページング セグメントに存在すると、他の基底クラスのメソッドやユーザー コードは、仮想メソッドの呼び出しによりページ フォールトがトリガーされないと見なすことがあります。

## <a name="example"></a>例

次の例では、暗黙的および明示的なテンプレートの特殊化が使用されている場合に、 **code_seg**属性がセグメントの配置を制御する方法を示します。

```cpp
// code_seg.cpp
// Compile: cl /EHsc /W4 code_seg.cpp

// Base template places object code in Segment_1 segment
template<class T>
class __declspec(code_seg("Segment_1")) Example
{
public:
   virtual void VirtualMemberFunction(T /*arg*/) {}
};

// bool specialization places code in default .text segment
template<>
class Example<bool>
{
public:
   virtual void VirtualMemberFunction(bool /*arg*/) {}
};

// int specialization places code in Segment_2 segment
template<>
class __declspec(code_seg("Segment_2")) Example<int>
{
public:
   virtual void VirtualMemberFunction(int /*arg*/) {}
};

// Compiler warns and ignores __declspec(code_seg("Segment_3"))
// in this explicit specialization
__declspec(code_seg("Segment_3")) Example<short>; // C4071

int main()
{
   // implicit double specialization uses base template's
   // __declspec(code_seg("Segment_1")) to place object code
   Example<double> doubleExample{};
   doubleExample.VirtualMemberFunction(3.14L);

   // bool specialization places object code in default .text segment
   Example<bool> boolExample{};
   boolExample.VirtualMemberFunction(true);

   // int specialization uses __declspec(code_seg("Segment_2"))
   // to place object code
   Example<int> intExample{};
   intExample.VirtualMemberFunction(42);
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
