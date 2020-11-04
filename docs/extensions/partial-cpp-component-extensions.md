---
title: partial (C++/CLI および C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- partial_CPP
helpviewer_keywords:
- partial
- C++/CX, partial
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
ms.openlocfilehash: 0f9de5dda1b0838a624431e579e6bc6b328d9013
ms.sourcegitcommit: d77159732a8e782b2a1b7abea552065f2b6f61c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "93344697"
---
# <a name="partial--ccli-and-ccx"></a>partial (C++/CLI および C++/CX)

**partial** キーワードを使用すると、同じ ref クラスの異なる部分を、別々のファイル内に作成できます。

## <a name="all-runtimes"></a>すべてのランタイム

(この言語機能は、Windows ランタイムにのみ適用されます。)

## <a name="windows-runtime"></a>Windows ランタイム

2つの部分定義を持つ ref クラスでは、 **partial** キーワードが最初に出現する定義に適用されます。これは通常、自動生成されたコードによって行われるため、人間のプログラマがキーワードを頻繁に使用しないようにします。 クラスの後続のすべての部分定義では、 *class-key* キーワードとクラス識別子から **partial** 修飾子を省略してください。 コンパイラで定義済みの ref クラスとクラス識別子が検出されたが、 **partial** キーワードがない場合は、ref クラス定義のすべての部分が 1 つの定義に内部的に結合されます。

### <a name="syntax"></a>構文

```cpp
partial class-key identifier {
   /* The first part of the partial class definition.
      This is typically auto-generated */
}
// ...
class-key identifier {
   /* The subsequent part(s) of the class definition. The same
      identifier is specified, but the "partial" keyword is omitted. */
}
```

### <a name="parameters"></a>パラメーター

*class-key*<br/>
Windows ランタイムによってサポートされるクラスまたは構造体を宣言するキーワード。 **ref class** 、 **value class** 、 **ref struct** 、または **value struct** のいずれか。

*identifier*<br/>
定義された型の名前。

### <a name="remarks"></a>注釈

部分クラスは、あるファイルの 1 つのクラス定義の一部分を変更したときに、XAML デザイナーなどの自動コード生成ソフトウェアによって、別のファイルの同じクラスが変更されるシナリオをサポートします。 部分クラスを使用することで、自動コードジェネレーターによるコードの上書きを防ぐことができます。 Visual Studio プロジェクトでは、生成されたファイルに **partial** 修飾子が自動的に適用されます。

内容: 2 つの例外を除き、部分クラス定義には、 **partial** キーワードが省略された場合に完全クラス定義に含めることができるすべてのものを含めることができます。 ただし、クラスのアクセシビリティ (例: `public partial class X { ... };`) または **declspec** は指定できません。

*identifier* の部分クラス定義で使用されるアクセス修飾子は、以降の部分定義または *identifier* の完全クラス定義の既定のアクセシビリティには影響しません。 静的データ メンバーのインライン定義が許可されます。

宣言: クラス *識別子* の部分定義では、名前 *識別子* だけが導入されますが、クラス定義を必要とする方法で *識別子* を使用することはできません。 コンパイラが *identifier* の完全定義を検出するまで、名前 *identifier* を使用して *identifier* のサイズを調べたり、 *identifier* の基底やメンバーを使用したりすることはできません。

数値と順序: *識別子* には、0個以上の部分クラス定義を指定できます。 *identifier* のすべての部分クラス定義は、構文上で 1 つの *identifier* の完全定義に先行する必要があります (完全定義がある場合。ない場合は、事前定義されているかのように使用する以外、このクラスを使用することはできません) が、 *identifier* の事前定義に先行する必要はありません。 すべての class-key が一致している必要があります。

完全な定義: クラス *識別子* の完全定義の時点での動作は、 *識別子* の定義で、すべての基底クラス、メンバーなどが、部分クラスで検出および定義された順序で宣言されている場合と同じです。

テンプレート: 部分クラスをテンプレートにすることはできません。

ジェネリック: 完全な定義がジェネリックである場合は、部分クラスをジェネリックにすることができます。 ただし、すべての部分クラスと完全クラスのジェネリック パラメーターは、パラメーターの正式名を含めて、完全に同じである必要があります。

**partial** キーワードの使用方法の詳細については、「 [部分クラス (C++/CX)](../cppcx/partial-classes-c-cx.md)」を参照してください。

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

(この言語機能は共通言語ランタイムには適用されません。)

## <a name="see-also"></a>関連項目

[部分クラス (C++/CX)](../cppcx/partial-classes-c-cx.md)
