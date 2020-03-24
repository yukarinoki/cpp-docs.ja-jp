---
title: /IGNORE (特定の警告を無視する)
ms.date: 11/04/2016
f1_keywords:
- /OVERWRITE
helpviewer_keywords:
- /IGNORE linker option
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
ms.openlocfilehash: c1f9374c168e5b21dfd761f8c984f00ceae9f1bc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170619"
---
# <a name="ignore-ignore-specific-warnings"></a>/IGNORE (特定の警告を無視する)

```
/IGNORE:warning[,warning]
```

## <a name="parameters"></a>パラメーター

*warning*<br/>
抑制するリンカー警告の番号 (範囲は 4000 ～ 4999)。

## <a name="remarks"></a>解説

既定では、LINK ではすべての警告が報告されます。 **[無視]** を指定します。これは、特定の警告番号を非表示にするようにリンカーに指示するために`warning` します。 複数の警告を無視するには、警告番号をコンマで区切ります。

リンカーで無視できない警告がいくつかあります。 次の表に、 **/IGNORE**によって抑制されない警告を示します。

|リンカー警告||
|--------------------|-|
|LNK4017|`keyword` ステートメントはターゲット プラットフォームでサポートされていません。無視しました。|
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|オプション '`option`' は無効です。無視されます。|
|LNK4062|'`option`' は、'`architecture`' 対象コンピューターと互換性がありません。オプションは無視されます|
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|"`option1`" は "`option2`"の指定によって無視されます。|
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|エントリポイント '`function`' は '`number`' バイトの引数を持つ __stdcall ではありません。イメージは動作しない可能性があります。|
|LNK4088|/FORCE オプションによってイメージが生成されています。イメージは動作しない可能性があります。|
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|オプション '`option`' に引数が指定されていません。オプションを無視します。|
|LNK4203|プログラム データベース '`filename`' の読み込み中にエラーが発生しました。デバッグ情報を無視してオブジェクトをリンクします。|
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|'`filename`' には参照するモジュールのデバッグ情報がありません。デバッグ情報がない場合と同様にオブジェクトをリンクしています|
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|'`filename`' には参照しているモジュールの現在のデバッグ情報がありません。デバッグ情報がない場合と同様にオブジェクトをリンクしています|
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|プリコンパイル済みの型情報が見つかりません。'`filename`' はリンクしていないか、上書きされています。|
|LNK4207|'`filename`' によってコンパイルされた/Yc/Yu/Z7;PDB を作成できません。/Zi を使用して再コンパイルします。デバッグ情報がない場合と同様にオブジェクトをリンクしています|
|LNK4208|'`filename`' 内の PDB 形式に互換性がありません。削除して再度ビルドしてください。デバッグ情報を無視してオブジェクトをリンクします。|
|LNK4209|デバッグ情報が壊れています。モジュールを再コンパイルしてください。デバッグ情報を無視してオブジェクトをリンクします。|
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option` はサポートされていません。無視されます。|
|LNK4228|'`option`' は DLL では無効です。無効|
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|無効なディレクティブ /`directive` が見つかりました。無視します。|

一般的に、無視できないリンカー警告は、修正する必要がある、ビルドの失敗、コマンド ラインのエラーまたは構成エラーを表します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関する記事を参照してください。

1. **[リンカー]** フォルダーで、 **[コマンドライン]** プロパティページを選択します。

1. [**追加オプション]** プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>) をご覧ください。
