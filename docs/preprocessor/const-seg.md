---
description: pragmaMicrosoft C/c + + での const_seg ディレクティブの詳細については、こちらを参照してください。
title: const_seg pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
helpviewer_keywords:
- pragma, const_seg
- const_seg pragma
no-loc:
- pragma
ms.openlocfilehash: 602ef749c966f9b28d7d6fa42a2bded1148bbe0d
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712922"
---
# <a name="const_seg-no-locpragma"></a>`const_seg` pragma

[Const](../cpp/const-cpp.md)変数がオブジェクト (.obj) ファイルに格納されるセクション (セグメント) を指定します。

## <a name="syntax"></a>構文

> **`#pragma const_seg(`** ["*section-name*" [ **`,`** "*section-class*"]] **`)`**\
> **`#pragma const_seg(`**{ **`push`**  |  **`pop`** } [ **`,`** *identifier* ] [ **`,`** "*section-name*" [ **`,`** "*section-class*"]]**`)`**

### <a name="parameters"></a>パラメーター

**`push`**\
Optional内部コンパイラスタックにレコードを格納します。 は **`push`** *識別子* と *セクション名* を持つことができます。

**`pop`**\
Optional内部コンパイラスタックの先頭からレコードを削除します。 は **`pop`** *識別子* と *セクション名* を持つことができます。 識別子を使用して、1つのコマンドだけを使用して複数のレコードをポップでき **`pop`** ます。  *セクション名* は、pop の後のアクティブな const セクション名になります。

*identifier*\
Optionalと共に使用すると **`push`** 、内部コンパイラスタックのレコードに名前を割り当てます。 と共に使用すると **`pop`** 、 *識別子* が削除されるまで、ディレクティブによってレコードが内部スタックからポップされます。 *識別子* が内部スタックで見つからない場合は、何もポップされません。

"*section-name*" \
Optionalセクションの名前。 と共に使用すると **`pop`** 、スタックがポップされ、 *セクション名* がアクティブな const セクション名になります。

"*セクションクラス*" \
Optionalは無視されますが、バージョン2.0 より前のバージョンの Microsoft C++ との互換性のために含まれています。

## <a name="remarks"></a>解説

オブジェクトファイルの *セクション* は、1つの単位としてメモリに読み込まれるデータの名前付きブロックです。 *Const セクション* は、定数データを含むセクションです。 この記事では、 *セグメント* と *セクション* は同じ意味を持ちます。

ディレクティブは、 **`const_seg`** pragma 翻訳単位のすべての定数データ項目を、 *セクション名* という名前の const セクションに配置するようコンパイラに指示します。 変数のオブジェクトファイルの既定のセクション **`const`** は `.rdata` です。 スカラーなどの一部の **`const`** 変数は、コードストリームに自動的にインライン化されます。 インラインコードはには表示されません `.rdata` 。 **`const_seg`** pragma *セクション名* パラメーターのないディレクティブは、後続のデータ項目のセクション名 **`const`** をにリセット `.rdata` します。

で動的な初期化を必要とするオブジェクトを定義した場合、 `const_seg` 結果は未定義の動作になります。

セクションの作成に使用しない名前の一覧については、「」を参照してください [`/SECTION`](../build/reference/section-specify-section-attributes.md) 。

初期化されたデータのセクション ( [`data_seg`](../preprocessor/data-seg.md) )、初期化されていないデータ ( [`bss_seg`](../preprocessor/bss-seg.md) )、および関数 () を指定することもでき [`code_seg`](../preprocessor/code-seg.md) ます。

[DUMPBIN.EXE](../build/reference/dumpbin-command-line.md)アプリケーションを使用して、オブジェクトファイルを表示できます。 サポートされている各ターゲットアーキテクチャの DUMPBIN のバージョンは、Visual Studio に含まれています。

## <a name="example"></a>例

```cpp
// pragma_directive_const_seg.cpp
// compile with: /EHsc
#include <iostream>

const int i = 7;               // inlined, not stored in .rdata
const char sz1[]= "test1";     // stored in .rdata

#pragma const_seg(".my_data1")
const char sz2[]= "test2";     // stored in .my_data1

#pragma const_seg(push, stack1, ".my_data2")
const char sz3[]= "test3";     // stored in .my_data2

#pragma const_seg(pop, stack1) // pop stack1 from stack
const char sz4[]= "test4";     // stored in .my_data1

int main() {
    using namespace std;
   // const data must be referenced to be put in .obj
   cout << sz1 << endl;
   cout << sz2 << endl;
   cout << sz3 << endl;
   cout << sz4 << endl;
}
```

```Output
test1
test2
test3
test4
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
