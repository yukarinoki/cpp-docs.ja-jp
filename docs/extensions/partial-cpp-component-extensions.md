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
ms.openlocfilehash: 42e8cc9a20c96e65ed3ddf73d562fe014bd9fa28
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350000"
---
# <a name="partial--ccli-and-ccx"></a>partial (C++/CLI および C++/CX)

**partial** キーワードを使用すると、同じ ref クラスの異なる部分を、別々のファイル内に作成できます。

## <a name="all-runtimes"></a>すべてのランタイム

(この言語機能は、Windows ランタイムにのみ適用されます。)

## <a name="windows-runtime"></a>Windows ランタイム

2 つの部分定義を持つ ref クラスの場合 **、partial**キーワードは定義の最初の出現に適用され、通常は自動生成されたコードによって行われるため、人間のコーダーはキーワードをあまり頻繁に使用しません。 クラスの後続のすべての部分定義では、*class-key* キーワードとクラス識別子から **partial** 修飾子を省略してください。 コンパイラで定義済みの ref クラスとクラス識別子が検出されたが、**partial** キーワードがない場合は、ref クラス定義のすべての部分が 1 つの定義に内部的に結合されます。

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
Windows ランタイムによってサポートされるクラスまたは構造体を宣言するキーワード。 **ref class**、**value class**、**ref struct**、または **value struct** のいずれか。

*識別子*<br/>
定義された型の名前。

### <a name="remarks"></a>解説

部分クラスは、あるファイルの 1 つのクラス定義の一部分を変更したときに、XAML デザイナーなどの自動コード生成ソフトウェアによって、別のファイルの同じクラスが変更されるシナリオをサポートします。 部分クラスを使用することで、自動コードジェネレーターによるコードの上書きを防ぐことができます。 Visual Studio プロジェクトでは、生成されたファイルに **partial** 修飾子が自動的に適用されます。

内容: 2 つの例外を除き、部分クラス定義には、**部分キーワードが**省略された場合に、完全なクラス定義に含まれる可能性のあるものを含めることができます。 ただし、クラスのアクセシビリティ (例: `public partial class X { ... };`) または **declspec** は指定できません。

*identifier* の部分クラス定義で使用されるアクセス修飾子は、以降の部分定義または *identifier* の完全クラス定義の既定のアクセシビリティには影響しません。 静的データ メンバーのインライン定義が許可されます。

宣言: クラス*識別子*の部分的な定義は名前*識別子*を導入するだけですが、*識別子*はクラス定義を必要とする方法では使用できません。 コンパイラが *identifier* の完全定義を検出するまで、名前 *identifier* を使用して *identifier* のサイズを調べたり、*identifier* の基底やメンバーを使用したりすることはできません。

数値と順序:*識別子*の部分クラス定義は 0 個以上存在する場合があります。 *identifier* のすべての部分クラス定義は、構文上で 1 つの *identifier* の完全定義に先行する必要があります (完全定義がある場合。ない場合は、事前定義されているかのように使用する以外、このクラスを使用することはできません) が、*identifier* の事前定義に先行する必要はありません。 すべての class-key が一致している必要があります。

完全定義: クラス*識別子*の完全な定義の時点では、*識別子*の定義が、部分クラスで検出され定義された順序ですべての基本クラス、メンバーなどを宣言した場合と同じ動作になります。

テンプレート: 部分クラスをテンプレートにすることはできません。

ジェネリック: 完全な定義がジェネリックである場合、部分クラスはジェネリックになることができます。 ただし、すべての部分クラスと完全クラスのジェネリック パラメーターは、パラメーターの正式名を含めて、完全に同じである必要があります。

**partial** キーワードの使用方法の詳細については、「[部分クラス (C++/CX)](https://go.microsoft.com/fwlink/p/?LinkId=249023)」を参照してください。

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

(この言語機能は共通言語ランタイムには適用されません。)

## <a name="see-also"></a>関連項目

[部分クラス (C++/CX)](https://go.microsoft.com/fwlink/p/?LinkId=249023)
