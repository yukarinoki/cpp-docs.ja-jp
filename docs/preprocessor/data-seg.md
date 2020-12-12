---
description: '詳細については、次を参照してください: data_seg プラグマ'
title: data_seg プラグマ
ms.date: 08/29/2019
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
helpviewer_keywords:
- data_seg pragma
- pragmas, data_seg
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
ms.openlocfilehash: f7caff65273b2fc0d51c6bfd1cede42cce7103d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300789"
---
# <a name="data_seg-pragma"></a>data_seg プラグマ

初期化された変数がオブジェクト (.obj) ファイルに格納されるデータセクション (セグメント) を指定します。

## <a name="syntax"></a>構文

> **#pragma data_seg (** ["*section-name*" [ **,** "*section-class*"]] **)**\
> **#pragma data_seg (** { **push**  |  **pop** } [ **,** *identifier* ] [ **,** "*section-name*" [ **,** "*section-class*"]] **)**

### <a name="parameters"></a>パラメーター

**押し付け**\
Optional内部コンパイラスタックにレコードを格納します。 **プッシュ** は *識別子* と *セクション名* を持つことができます。

**ショート**\
Optional内部コンパイラスタックの先頭からレコードを削除します。 **Pop** は *識別子* と *セクション名* を持つことができます。 *識別子* を使用して、 **pop** コマンドを1つだけ使用して複数のレコードをポップできます。 *セクション名* は、pop の後のアクティブなデータセクション名になります。

*identifier*\
Optional **Push** と共に使用すると、内部コンパイラスタックのレコードに名前が割り当てられます。 **Pop** と共に使用すると、*識別子* が削除されるまでレコードを内部スタックからポップします。 *識別子* が内部スタックで見つからない場合は、何もポップされません。

*識別子* を使用すると、複数のレコードを1つの **pop** コマンドでポップできます。

*"section-name"*\
Optionalセクションの名前。 **Pop** と共に使用すると、スタックがポップされ、*セクション名* がアクティブなデータセクション名になります。

*"セクション-クラス"*\
Optionalは無視されますが、バージョン2.0 より前のバージョンの Microsoft C++ との互換性のために含まれています。

## <a name="remarks"></a>解説

オブジェクトファイルの *セクション* は、1つの単位としてメモリに読み込まれるデータの名前付きブロックです。 *データセクション* は、初期化されたデータを含むセクションです。 この記事では、 *セグメント* と *セクション* は同じ意味を持ちます。

初期化された変数の .obj ファイルの既定のセクションは `.data` です。 初期化されていない変数はゼロに初期化され、に格納され `.bss` ます。

**Data_seg** プラグマディレクティブは、翻訳単位から初期化されたすべてのデータ項目を、*セクション名* という名前のデータセクションに配置するようにコンパイラに指示します。 既定では、オブジェクトファイル内の初期化されたデータに使用される data セクションにはという名前が付けられ `.data` ます。 初期化されていない変数は0に初期化されると見なされ、に格納され `.bss` ます。 *セクション名* パラメーターを指定せずに **data_seg** プラグマディレクティブを実行すると、その後の初期化されたデータ項目のデータセクション名がにリセットさ `.data` れます。

**Data_seg** を使用して割り当てられたデータには、その場所に関する情報は保持されません。

セクションの作成に使用しない名前の一覧については、「 [/SECTION](../build/reference/section-specify-section-attributes.md)」を参照してください。

Const 変数のセクション ([const_seg](../preprocessor/const-seg.md))、初期化されていないデータ ([bss_seg](../preprocessor/bss-seg.md))、および関数 ([code_seg](../preprocessor/code-seg.md)) を指定することもできます。

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

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
