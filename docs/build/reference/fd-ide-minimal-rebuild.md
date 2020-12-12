---
description: 詳細情報:/FD (IDE の簡易リビルド)
title: /FD (IDE の簡易リビルド)
ms.date: 04/08/2019
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: d9b2a91c14b80890c703b8f4dd5b2de3aefb012b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192292"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (IDE の簡易リビルド)

**/Fd** は、C++ プロジェクトの [**プロパティページ**] ダイアログボックスの [[コマンドライン](command-line-property-pages.md)] プロパティページでのみユーザーに公開されます。 [非推奨の [/Gm (最小リビルドを有効にする)](gm-enable-minimal-rebuild.md) ] オプションが選択されていない場合にのみ使用できます。 **/Fd** は、開発環境以外には効果がありません。 **/Fd** は、の出力では公開されません `cl /?` 。

開発環境で非推奨の **/Gm** オプションを有効にしない場合は、 **/fd** が使用されます。 **/Fd** は、.idb ファイルに十分な依存関係情報があることを確認します。 **/Fd** は開発環境でのみ使用され、コマンドラインやビルドスクリプトからは使用できません。

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
