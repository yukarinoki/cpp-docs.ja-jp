---
description: 詳細については、「リンカーツールの警告 LNK4075」を参照してください。
title: リンカー ツールの警告 LNK4075
ms.date: 11/04/2016
f1_keywords:
- LNK4075
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
ms.openlocfilehash: d7883573271522857b34b3aac81bf45029e540ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210154"
---
# <a name="linker-tools-warning-lnk4075"></a>リンカー ツールの警告 LNK4075

"option2" の指定により、"オプション 1" は無視される

2番目のオプションは、最初のオプションをオーバーライドします。

相互に排他的なリンカーオプションが指定されています。  リンカーオプションを確認します。  リンカーオプションを指定する場所は、プロジェクトのビルド方法によって異なります。

- 開発環境でビルドする場合は、プロジェクトの [リンカー] プロパティページを調べ、両方のリンカーオプションが指定されている場所を確認します。  詳細については [、「コンパイラとビルドのプロパティの設定](../../build/working-with-project-properties.md) 」を参照してください。

- コマンドラインでビルドする場合は、そこに指定されているリンカーオプションを確認します。

- ビルドスクリプトでビルドする場合は、スクリプトを参照して、リンカーオプションが指定されている場所を確認します。

相互排他的なリンカーオプションを指定する場合は、いずれかのリンカーオプションを削除します。

いくつかの例を次に示します。

- **/Zi** を使用してコンパイルされたモジュールをリンクする場合、これは/editandcontinue という内部リンカーオプションと、/OPT: REF、/OPT: ICF、または/INCREMENTAL: no を指定してコンパイルされたモジュールで、LNK4075 を取得します。  詳細については [、「/Z7、/zi、/zi (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md) 」を参照してください。
