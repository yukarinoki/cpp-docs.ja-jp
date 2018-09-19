---
title: -FD (IDE の簡易リビルド) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /FD
dev_langs:
- C++
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74fb35ec25bed808e2165498c00b65723aba5bac
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702443"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (IDE の簡易リビルド)

**/FD**以外でのユーザーに公開されていない、[コマンドライン](../../ide/command-line-property-pages.md)の C++ プロジェクトのプロパティ ページ**プロパティ ページ**] ダイアログ ボックスの [場合にのみ、 [/Gm (簡易リビルドの有効)](../../build/reference/gm-enable-minimal-rebuild.md)も選択されていません。 **/FD**以外の開発環境からの影響を与えません。 **/FD**の出力で公開されていない**cl/でしょうか。** します。

有効にしない場合 **/Gm** 、開発環境で **/FD**使用されます。 **/FD** .idb ファイルに依存関係のための十分な情報があることを確認します。 **/FD**は、開発環境でのみ使用、コマンドラインまたはビルド スクリプトから使用する必要があります。

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)