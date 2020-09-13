---
title: /IGNORE (特定の警告を無視する)
ms.date: 11/04/2016
f1_keywords:
- /OVERWRITE
helpviewer_keywords:
- /IGNORE linker option
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
ms.openlocfilehash: 4ed87a1a12bea189f56545cf5256351a29977643
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040263"
---
# <a name="ignore-ignore-specific-warnings"></a>/IGNORE (特定の警告を無視する)

```
/IGNORE:warning[,warning]
```

## <a name="parameters"></a>パラメーター

*warning*<br/>
抑制するリンカー警告の番号 (範囲は 4000 ～ 4999)。

## <a name="remarks"></a>注釈

既定では、LINK ではすべての警告が報告されます。 **「/IGNORE:** 」と指定 `warning` すると、特定の警告番号を抑制するようにリンカーに指示します。 複数の警告を無視するには、警告番号をコンマで区切ります。

リンカーで無視できない警告がいくつかあります。 次の表に、 **/IGNORE**によって抑制されない警告を示します。

| リンカー警告 | メッセージ |
|--------------------|-|
|LNK4017|`keyword` ステートメントはターゲット プラットフォームでサポートされていません。無視しました。|
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|オプション '`option`' は無効です。無視されます。|
|LNK4062|' ' は `option` ターゲットコンピューター ' ' と互換性がありません `architecture` 。オプションは無視されます。|
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|"`option1`" は "`option2`"の指定によって無視されます。|
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|エントリポイント '`function`' は '`number`' バイトの引数を持つ __stdcall ではありません。イメージは動作しない可能性があります。|
|LNK4088|/FORCE オプションによってイメージが生成されています。イメージは動作しない可能性があります。|
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|オプション '`option`' に引数が指定されていません。オプションを無視します。|
|LNK4203|プログラム データベース '`filename`' の読み込み中にエラーが発生しました。デバッグ情報を無視してオブジェクトをリンクします。|
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|' `filename` ' に参照するモジュールのデバッグ情報がありません。デバッグ情報がないかのようにオブジェクトをリンクします。|
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|' `filename` ' に参照するモジュールの現在のデバッグ情報がありません。デバッグ情報がないかのようにオブジェクトをリンクします。|
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|プリコンパイル済みの型情報が見つかりません。'`filename`' はリンクしていないか、上書きされています。|
|LNK4207|' `filename` ' コンパイルされた/Yc/Yu/Z7; PDB を作成できません。/zi を使用して再コンパイルします。デバッグ情報がないかのようにオブジェクトをリンクします|
|LNK4208|'`filename`' 内の PDB 形式に互換性がありません。削除して再度ビルドしてください。デバッグ情報を無視してオブジェクトをリンクします。|
|LNK4209|デバッグ情報が壊れています。モジュールを再コンパイルしてください。デバッグ情報を無視してオブジェクトをリンクします。|
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option` はサポートされていません。無視されます。|
|LNK4228|' `option` ' は DLL では無効です。無視されます。|
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|無効なディレクティブ /`directive` が見つかりました。無視します。|

一般的に、無視できないリンカー警告は、修正する必要がある、ビルドの失敗、コマンド ラインのエラーまたは構成エラーを表します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **リンカー** ] フォルダーで、[ **コマンドライン** ] プロパティページを選択します。

1. [ **追加オプション]** プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>
