---
description: pragmaMicrosoft C/c + + での code_seg ディレクティブの詳細については、こちらを参照してください。
title: code_seg pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.code_seg
helpviewer_keywords:
- pragma, code_seg
- code_seg pragma
no-loc:
- pragma
ms.openlocfilehash: 0547c745fe5d22be3684e83e0dcc2c73e13e8edc
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713103"
---
# <a name="code_seg-no-locpragma"></a>`code_seg` pragma

関数がオブジェクト (.obj) ファイルに格納されるテキストセクション (セグメント) を指定します。

## <a name="syntax"></a>構文

> **`#pragma code_seg(`** ["*section-name*" [ **`,`** "*section-class*"]] **`)`**\
> **`#pragma code_seg(`**{ **`push`**  |  **`pop`** } [ **`,`** *identifier* ] [ **`,`** "*section-name*" [ **`,`** "*section-class*"]]**`)`**

### <a name="parameters"></a>パラメーター

**`push`**\
Optional内部コンパイラスタックにレコードを格納します。 は **`push`** *識別子* と *セクション名* を持つことができます。

**`pop`**\
Optional内部コンパイラスタックの先頭からレコードを削除します。 は **`pop`** *識別子* と *セクション名* を持つことができます。 識別子を使用して、1つのコマンドだけを使用して複数のレコードをポップでき **`pop`** ます。  *セクション名* は、pop の後のアクティブなテキストセクション名になります。

*identifier*\
Optionalと共に使用すると **`push`** 、内部コンパイラスタックのレコードに名前を割り当てます。 と共に使用すると **`pop`** 、 *識別子* が削除されるまで、ディレクティブによってレコードが内部スタックからポップされます。 *識別子* が内部スタックで見つからない場合は、何もポップされません。

"*section-name*" \
Optionalセクションの名前。 と共に使用すると **`pop`** 、スタックがポップされ、 *セクション名* がアクティブなテキストセクション名になります。

"*セクションクラス*" \
Optionalは無視されますが、バージョン2.0 より前のバージョンの Microsoft C++ との互換性のために含まれています。

## <a name="remarks"></a>解説

オブジェクトファイルの *セクション* は、1つの単位としてメモリに読み込まれるデータの名前付きブロックです。 *テキストセクション* は、実行可能コードを含むセクションです。 この記事では、 *セグメント* と *セクション* は同じ意味を持ちます。

ディレクティブは、 **`code_seg`** pragma 翻訳単位の後続のすべてのオブジェクトコードを、 *セクション名* という名前のテキストセクションに配置するようにコンパイラに指示します。 既定では、オブジェクトファイルの関数に使用される text セクションにはという名前が付けられ `.text` ます。 **`code_seg`** pragma *セクション名* パラメーターのないディレクティブは、その後のオブジェクトコードのテキストセクション名をにリセット `.text` します。

ディレクティブは、 **`code_seg`** pragma インスタンス化されたテンプレート用に生成されたオブジェクトコードの配置を制御しません。 また、特殊なメンバー関数など、コンパイラによって暗黙的に生成されるコードも制御しません。 このコードを制御するには、代わりに属性を使用することをお勧めし [`__declspec(code_seg(...))`](../cpp/code-seg-declspec.md) ます。 コンパイラによって生成されるコードを含め、すべてのオブジェクトコードの配置を制御できます。

セクションの作成に使用しない名前の一覧については、「」を参照してください [`/SECTION`](../build/reference/section-specify-section-attributes.md) 。

初期化されたデータのセクション ( [`data_seg`](../preprocessor/data-seg.md) )、初期化されていないデータ ( [`bss_seg`](../preprocessor/bss-seg.md) )、および const 変数 () を指定することもでき [`const_seg`](../preprocessor/const-seg.md) ます。

[DUMPBIN.EXE](../build/reference/dumpbin-command-line.md)アプリケーションを使用して、オブジェクトファイルを表示できます。 サポートされている各ターゲットアーキテクチャの DUMPBIN のバージョンは、Visual Studio に含まれています。

## <a name="example"></a>例

この例では、 **code_seg** ディレクティブを使用して、 pragma オブジェクトコードの配置場所を制御する方法を示します。

```cpp
// pragma_directive_code_seg.cpp
void func1() {                  // stored in .text
}

#pragma code_seg(".my_data1")
void func2() {                  // stored in my_data1
}

#pragma code_seg(push, r1, ".my_data2")
void func3() {                  // stored in my_data2
}

#pragma code_seg(pop, r1)      // stored in my_data1
void func4() {
}

int main() {
}
```

## <a name="see-also"></a>関連項目

[`code_seg (__declspec)`](../cpp/code-seg-declspec.md)\
[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
