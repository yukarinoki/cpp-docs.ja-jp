---
title: /FD (IDE の簡易リビルド)
ms.date: 04/08/2019
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: 896adcb97a259e6714cf23241424841456371491
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439807"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (IDE の簡易リビルド)

**/Fd**は、 C++プロジェクトの **[プロパティページ]** ダイアログボックスの [[コマンドライン](command-line-property-pages.md)] プロパティページでのみユーザーに公開されます。 [非推奨の[/Gm (最小リビルドを有効にする)](gm-enable-minimal-rebuild.md) ] オプションが選択されていない場合にのみ使用できます。 **/Fd**は、開発環境以外には効果がありません。 `cl /?`の出力では、 **/fd**は公開されていません。

開発環境で非推奨の **/Gm**オプションを有効にしない場合は、 **/fd**が使用されます。 **/Fd**は、.idb ファイルに十分な依存関係情報があることを確認します。 **/Fd**は開発環境でのみ使用され、コマンドラインやビルドスクリプトからは使用できません。

## <a name="see-also"></a>参照

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
