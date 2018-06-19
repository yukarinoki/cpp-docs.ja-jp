---
title: -無視 (特定の警告を無視する) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /OVERWRITE
dev_langs:
- C++
helpviewer_keywords:
- /IGNORE linker option
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b096fc12f69fbe637a3067646c20f6d520a9250f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378010"
---
# <a name="ignore-ignore-specific-warnings"></a>/IGNORE (特定の警告を無視する)
```  
/IGNORE:warning[,warning]  
```  
  
## <a name="parameters"></a>パラメーター  
 `warning`  
 抑制するリンカー警告の番号 (範囲は 4000 ～ 4999)。  
  
## <a name="remarks"></a>コメント  
 既定では、LINK ではすべての警告が報告されます。 指定**の無視:** `warning`への特定の警告番号を抑制するようにリンカーを通知します。 複数の警告を無視するには、警告番号をコンマで区切ります。  
  
 リンカーで無視できない警告がいくつかあります。 次の表の一覧によって抑制されない警告 **/ignore**:  
  
|リンカー警告||  
|--------------------|-|  
|LNK4017|`keyword` ステートメントはターゲット プラットフォームでサポートされていません。無視しました。|  
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|オプション '`option`' は無効です。無視されます。|  
|LNK4062|'`option`'と互換性がありません'`architecture`' 対象コンピューター以外のオプションは無視されます|  
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|"`option1`" は "`option2`"の指定によって無視されます。|  
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|エントリポイント '`function`' は '`number`' バイトの引数を持つ __stdcall ではありません。イメージは動作しない可能性があります。|  
|LNK4088|/FORCE オプションによってイメージが生成されています。イメージは動作しない可能性があります。|  
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|オプション '`option`' に引数が指定されていません。オプションを無視します。|  
|LNK4203|プログラム データベース '`filename`' の読み込み中にエラーが発生しました。デバッグ情報を無視してオブジェクトをリンクします。|  
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|'`filename`' 参照するモジュールのデバッグ情報がないオブジェクトをリンク デバッグ情報がありません|  
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|'`filename`' が参照するモジュールの現在のデバッグ情報のないオブジェクトをリンク デバッグ情報がありません|  
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|プリコンパイル済みの型情報が見つかりません。'`filename`' はリンクしていないか、上書きされています。|  
|LNK4207|'`filename`'/Yc/Yu/Z7 をコンパイル デバッグ情報がない場合と PDB;/Zi で再コンパイル、リンク オブジェクトを作成できません。|  
|LNK4208|'`filename`' 内の PDB 形式に互換性がありません。削除して再度ビルドしてください。デバッグ情報を無視してオブジェクトをリンクします。|  
|LNK4209|デバッグ情報が壊れています。モジュールを再コンパイルしてください。デバッグ情報を無視してオブジェクトをリンクします。|  
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option` はサポートされていません。無視されます。|  
|LNK4228|'`option`' dll が無効です。 無視されます。|  
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|無効なディレクティブ /`directive` が見つかりました。無視します。|  
  
 一般的に、無視できないリンカー警告は、修正する必要がある、ビルドの失敗、コマンド ラインのエラーまたは構成エラーを表します。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **リンカー**フォルダーを選択、**コマンドライン**プロパティ ページ。  
  
3.  変更、**追加オプション**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。