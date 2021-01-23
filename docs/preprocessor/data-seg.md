---
description: pragmaMicrosoft C/c + + での data_seg ディレクティブの詳細については、こちらを参照してください。
title: data_seg pragma
ms.date: 01/22/2021
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
helpviewer_keywords:
- data_seg pragma
- pragma, data_seg
no-loc:
- pragma
ms.openlocfilehash: cd0dac6961a642b8ed2bd5d485712d259d828a64
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713689"
---
# <a name="data_seg-no-locpragma"></a>`data_seg` pragma

初期化された変数がオブジェクト (.obj) ファイルに格納されるデータセクション (セグメント) を指定します。

## <a name="syntax"></a>構文

> **`#pragma data_seg(`** ["*section-name*" [ **`,`** "*section-class*"]] **`)`**\
> **`#pragma data_seg(`**{ **`push`**  |  **`pop`** } [ **`,`** *identifier* ] [ **`,`** "*section-name*" [ **`,`** "*section-class*"]]**`)`**

### <a name="parameters"></a>パラメーター

**`push`**\
Optional内部コンパイラスタックにレコードを格納します。 は **`push`** *識別子* と *セクション名* を持つことができます。

**`pop`**\
Optional内部コンパイラスタックの先頭からレコードを削除します。 は **`pop`** *識別子* と *セクション名* を持つことができます。 識別子を使用して、1つのコマンドだけを使用して複数のレコードをポップでき **`pop`** ます。  *セクション名* は、pop の後のアクティブなデータセクション名になります。

*identifier*\
Optionalと共に使用すると **`push`** 、内部コンパイラスタックのレコードに名前を割り当てます。 と共に使用すると **`pop`** 、 *識別子* が削除されるまで、レコードは内部スタックからポップされます。 *識別子* が内部スタックで見つからない場合は、何もポップされません。

*識別子* を使用すると、1つのコマンドで複数のレコードをポップでき **`pop`** ます。

*"section-name"*\
Optionalセクションの名前。 と共に使用すると **`pop`** 、スタックがポップされ、 *セクション名* がアクティブなデータセクション名になります。

*"セクション-クラス"*\
Optionalは無視されますが、バージョン2.0 より前のバージョンの Microsoft C++ との互換性のために含まれています。

## <a name="remarks"></a>解説

オブジェクトファイルの *セクション* は、1つの単位としてメモリに読み込まれるデータの名前付きブロックです。 *データセクション* は、初期化されたデータを含むセクションです。 この記事では、 *セグメント* と *セクション* は同じ意味を持ちます。

初期化された変数の .obj ファイルの既定のセクションは `.data` です。 初期化されていない変数はゼロに初期化され、に格納され `.bss` ます。

ディレクティブは、 **`data_seg`** pragma 翻訳単位から初期化されたすべてのデータ項目を、 *セクション名* という名前のデータセクションに配置するようにコンパイラに指示します。 既定では、オブジェクトファイル内の初期化されたデータに使用される data セクションにはという名前が付けられ `.data` ます。 初期化されていない変数は0に初期化されると見なされ、に格納され `.bss` ます。 **`data_seg`** pragma *セクション名* パラメーターのないディレクティブは、後続の初期化されたデータ項目のデータセクション名をにリセット `.data` します。

を使用して割り当てられたデータは **`data_seg`** 、その場所に関する情報を保持しません。

セクションの作成に使用しない名前の一覧については、「」を参照してください [`/SECTION`](../build/reference/section-specify-section-attributes.md) 。

Const 変数 ( [`const_seg`](../preprocessor/const-seg.md) )、初期化されていないデータ ( [`bss_seg`](../preprocessor/bss-seg.md) )、および関数 () のセクションを指定することもでき [`code_seg`](../preprocessor/code-seg.md) ます。

[DUMPBIN.EXE](../build/reference/dumpbin-command-line.md)アプリケーションを使用して、オブジェクトファイルを表示できます。 サポートされている各ターゲットアーキテクチャの DUMPBIN のバージョンは、Visual Studio に含まれています。

## <a name="example"></a>例

```cpp
// pragma_directive_data_seg.cpp
int h = 1;                     // stored in .data
int i = 0;                     // stored in .bss
#pragma data_seg(".my_data1")
int j = 1;                     // stored in .my_data1

#pragma data_seg(push, stack1, ".my_data2")
int l = 2;                     // stored in .my_data2

#pragma data_seg(pop, stack1)   // pop stack1 off the stack
int m = 3;                     // stored in .my_data1

int main() {
}
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
