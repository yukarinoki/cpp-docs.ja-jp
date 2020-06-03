---
title: /Gm (簡易リビルドの有効化)
ms.date: 11/12/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
ms.openlocfilehash: 9b928f3add0a2ec10257bf63fe61a824336c19b8
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439647"
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm (簡易リビルドの有効化)

非推奨。 最小リビルドを有効にします。最小リビルドにより、(ヘッダー (.h) ファイルに格納されている) 変更された C++ クラス定義を含む C++ ソース ファイルを再コンパイルする必要があるかどうかが決定されます。

## <a name="syntax"></a>構文

```
/Gm
```

## <a name="remarks"></a>コメント

**/Gm**は非推奨とされます。 特定の種類のヘッダーファイルの変更に対しては、ビルドがトリガーされない場合があります。 このオプションは、プロジェクトから安全に削除できます。 ビルド時間を短縮するには、プリコンパイル済みヘッダーと増分および並列ビルドオプションを使用することをお勧めします。 非推奨のコンパイラオプションの一覧については、「[カテゴリ別のコンパイラオプション](compiler-options-listed-by-category.md)」の「**非推奨のコンパイラオプション**」セクションを参照してください。

最初のコンパイル時に、コンパイラによってソース ファイルとクラス定義の間の依存関係情報がプロジェクトの .idb ファイルに格納されます。 (依存関係情報は、どのソース ファイルがどのクラス定義に依存し、どの .h ファイルに定義があるかを示します)。その後のコンパイルでは、.idb ファイルに格納されている情報が使用され、変更された .h ファイルが含まれている場合でも、ソース ファイルをコンパイルする必要があるかどうかが決定されます。

> [!NOTE]
> 最小リビルドは、クラス定義がインクルード ファイル間で変わらないことに依存します。 .idb ファイル内の依存関係情報はプロジェクト全体に対して作成されるため、クラス定義はプロジェクトに対してグローバルである必要があります (特定のクラスの定義は 1 つのみである必要があります)。 プロジェクト内のクラスに複数の定義がある場合は、最小リビルドを無効にします。

インクリメンタルリンカーは[/ZW (Windows ランタイムコンパイル)](zw-windows-runtime-compilation.md)オプションを使用して .obj ファイルに含まれる Windows メタデータをサポートしていないため、 **/Gm**オプションは **/ZW**と互換性がありません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関する記事を参照してください。

1. **[構成プロパティ]**  > [ **CC++ /**  > **コード生成**] プロパティページを選択します。

1. **[最小リビルドを有効にする]** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>) をご覧ください。

## <a name="see-also"></a>参照

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
