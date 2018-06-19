---
title: /SECTION (セクション属性の指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /section
dev_langs:
- C++
helpviewer_keywords:
- SECTION linker option
- -SECTION linker option
- section attributes
- /SECTION linker option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d9b0a724f0e9156c81db20bf283e4418dd2f22d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379524"
---
# <a name="section-specify-section-attributes"></a>/SECTION (セクション属性の指定)

> **/SECTION:**_名前_、**[!]**{**DEKPRSW**}] [**、ALIGN =**_数_]

## <a name="remarks"></a>コメント

**/Section**オプションは、セクションの .obj ファイルがコンパイルされたときに設定した属性をオーバーライドするセクションの属性を変更します。

A*セクション*ポータブル実行可能 (PE) ファイルは、名前付き連続したメモリ ブロックをコードまたはデータが含まれています。 いくつかのセクションでは、コードまたはプログラムが宣言されており、データのセクションではその他のリンカーと (lib.exe) ライブラリ マネージャーで作成し、オペレーティング システムに不可欠な情報が含まれてときに、直接使用するデータを格納します。 詳細については、次を参照してください。 [PE 形式](https://msdn.microsoft.com/library/windows/desktop/ms680547)です。

コロン (:) およびセクションを指定*名前*です。 *名前*大文字小文字を区別します。

標準の名前と競合すると、次の名前を使わないでください。 たとえば、.sdata は RISC プラットフォームで使用されます。

- .arch

- .bss

- .data

- .edata

- .idata

- .pdata

- .rdata

- .reloc

- .rsrc

- .sbss

- .sdata

- .srdata

- .text

- .xdata

セクションの 1 つまたは複数の属性を指定します。 次に、属性文字が大文字と小文字ではありません。 セクションに必要です。 対象となるすべての属性を指定する必要があります。属性が省略された文字では、オフにするには、その属性ビットが発生します。 R、W、または E、既存の読み取り、書き込み、指定しない場合は実行可能ファイルの状態は変更されません。

属性を符号反転するには、感嘆符 (!) 付きの文字の前にします。 属性の文字の意味は次の表に示します。

|文字|属性|説明|
|---------------|---------------|-------------|
|E|実行|セクションが実行可能ファイル|
|R|読み取り|データの読み取り操作します。|
|W|書き込み|データの書き込み操作します。|
|S|共有|イメージを読み込むすべてのプロセス間でセクションを共有します|
|D|破棄可能|セクション破棄可能にします|
|K|キャッシュ可能です|セクションをキャッシュ不可としてマークを付けます|
|P|ページング可能です|セクションをページング不可としてマークを付けます|

K および P はない通常それらに対応するセクション フラグは負の値の意味で使用されます。 かどうかを指定する 1 つは .text セクションでを使用して、 **/SECTION:.text, K**オプションを実行すると、セクション フラグに違いはありません[DUMPBIN](../../build/reference/dumpbin-options.md)で、 [/HEADERS](../../build/reference/headers.md)オプションです。セクションが暗黙的に既にキャッシュされてます。 既定値を削除する指定 **/SECTION:.text、!K**代わりにします。 DUMPBIN「キャッシュされません」を含む、セクションの特性を表示します。

電子メール、R、または W の設定を持たない PE ファイルのセクションの可能性がありますが正しくありません。

**ALIGN =**_数_引数では、特定のセクションのアラインメント値を指定することができます。 _数_引数をバイト単位で、2 の累乗にする必要があります。 参照してください[配置/](../../build/reference/align-section-alignment.md)詳細についてはします。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. オプションを入力して、**追加オプション**ボックス。 選択**OK**または**適用**変更を適用します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)  
[リンカー オプション](../../build/reference/linker-options.md)  
