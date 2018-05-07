---
title: 'HLSL プロパティ ページ: 全般 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
dev_langs:
- C++
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77cc9a44076999633fd17b049cbcfad75f65eb7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hlsl-property-pages-general"></a>[全般] ([HLSL] プロパティ ページ)
HLSL コンパイラ (fxc.exe) の次のプロパティを構成するのには、使用、**全般**プロパティ ページ。 アクセスする方法については、**全般**HLSL フォルダー内のプロパティ ページを参照してください[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **追加のインクルード ディレクトリ**  
 インクルード パスに 1 つまたは複数のディレクトリを追加します。 セミコロンを使用して、ディレクトリを区切ります。  
  
 このプロパティに対応、 **/I [パス]** コマンドライン引数。  
  
 **エントリ ポイント名**  
 シェーダーのエントリ ポイントを指定します。 値は、既定では、**メイン**です。  
  
 このプロパティに対応、 **/E [名前]** コマンドライン引数。  
  
 **最適化を無効にします。**  
 **はい (/Od)** 最適化を無効にするそれ以外の場合、**いいえ**です。 値は、既定では、**はい (/Od)** の**デバッグ**構成と**いいえ**の**リリース**構成します。  
  
 **/Od** HLSL コンパイラのコマンドライン引数が暗黙的に適用されます、 **/gfp とは異なる**コマンドラインの引数が出力をどちらも渡すことによって生成される出力と同じできない可能性があります、 **/Od**と **/gfp とは異なる**コマンドライン引数に明示的にします。  
  
 **デバッグ情報を有効にします。**  
 **はい (/Zi)** 情報のデバッグを有効にするそれ以外の場合、**いいえ**です。 値は、既定では、 **(/Zi) を [はい]** の**デバッグ**構成と**いいえ**の**リリース**構成します。  
  
 **シェーダーの種類**  
 シェーダーの種類を指定します。 シェーダーのさまざまな種類では、グラフィックス パイプラインのさまざまな部分を実装します。 シェーダーの種類によっては、最新のシェーダー モデルでのみ使用できます (で指定されている、 **Shader Model**プロパティ) — たとえば、計算シェーダーが 5 のシェーダー モデルで導入されました。  
  
 このプロパティに対応、 **[種類]** の部分、 **/T [種類] _ [モデル]** HLSL コンパイラのコマンドライン引数。 **のシェーダー モデル**プロパティを指定します、 **[モデル]** 引数の部分です。  
  
 **シェーダー モデル**  
 シェーダー モデルを指定します。 別のシェーダー モデルでは、異なる機能があります。 一般より最新のシェーダー モデルは拡張機能を提供しますが、シェーダー コードを実行する最新のグラフィックス ハードウェアを必要とします。 シェーダーの特定の種類 (で指定されている、**シェーダー型**プロパティ) が最新のシェーダー モデルでのみ使用できます: たとえば、計算シェーダーが 5 のシェーダー モデルで導入されました。  
  
 このプロパティに対応、 **[モデル]** の部分、 **/T [種類] _ [モデル]** HLSL コンパイラのコマンドライン引数。 **シェーダー型**プロパティを指定します、 **[種類]** 引数の部分です。  
  
 **プリプロセッサの定義**  
 HLSL のソース コード ファイルに適用する 1 つ以上のプリプロセッサ シンボル定義を追加します。 セミコロンを使用して、シンボル定義を区切ります。  
  
 このプロパティに対応、 **/D [定義]** HLSL コンパイラのコマンドライン引数。  
  
## <a name="see-also"></a>関連項目  
 [[HLSL] プロパティ ページ](../ide/hlsl-property-pages.md)   
 [[HLSL] プロパティ ページ: 高度な](../ide/hlsl-property-pages-advanced.md)   
 [[HLSL] プロパティ ページ: 出力ファイル](../ide/hlsl-property-pages-output-files.md)