---
title: リンカー オプションの設定 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2fd99732c7f79b3c61ff5b31516b98a478ed4a8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713077"
---
# <a name="setting-linker-options"></a>リンカー オプションの設定

開発環境の内外で、リンカー オプションを設定できます。 各リンカー オプションのトピックでは、開発環境で設定する方法について説明します。 参照してください[リンカー オプション](../../build/reference/linker-options.md)完全な一覧についてはします。

開発環境の外部リンクを実行する場合は、1 つまたは複数の方法で入力を指定できます。

- [コマンドライン](../../build/reference/linker-command-line-syntax.md)

- 使用して[コマンド ファイル](../../build/reference/link-command-files.md)

- [環境変数](../../build/reference/link-environment-variables.md)

その後にオプションおよびコマンド ファイル、コマンドラインで指定された順序で、リンクの環境変数でリンク最初プロセス オプションを指定します。 オプションは引数を繰り返し、処理された最後の 1 つが優先されます。

オプションは、すべてのビルドに適用されます。特定の入力ファイルをオプションを適用しないことができます。

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)