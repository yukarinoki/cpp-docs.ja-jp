---
title: EDITBIN リファレンス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 809d1d4f25611b2310d651702f01e1e98888ad4a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699948"
---
# <a name="editbin-reference"></a>EDITBIN リファレンス

Microsoft COFF バイナリ ファイル エディター (EDITBIN します。EXE) は、一般的なオブジェクト ファイル形式 (COFF) のバイナリ ファイルを変更します。 EDITBIN を使用して、オブジェクト ファイル、実行可能ファイル、およびダイナミック リンク ライブラリ (DLL) を変更することができます。

> [!NOTE]
>  このツールは、Visual Studio コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。

EDITBIN がで生成されたファイルで使用できる、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。 /GL で生成されたバイナリ ファイルの変更は、再コンパイルとリンクで実現する必要があります。

- [EDITBIN コマンドライン](../../build/reference/editbin-command-line.md)

- [EDITBIN オプション](../../build/reference/editbin-options.md)

## <a name="see-also"></a>関連項目

[C/C++ のビルド ツール](../../build/reference/c-cpp-build-tools.md)