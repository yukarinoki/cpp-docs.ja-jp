---
description: 詳細については、「EDITBIN リファレンス」を参照してください。
title: EDITBIN リファレンス
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
ms.openlocfilehash: ad211ab85ac00cd716b7c3b8e381a9a448ea04ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201028"
---
# <a name="editbin-reference"></a>EDITBIN リファレンス

Microsoft COFF バイナリファイルエディター (EDITBIN.EXE) では、COFF (Common Object File Format) バイナリファイルが変更されます。 EDITBIN を使用して、オブジェクトファイル、実行可能ファイル、およびダイナミックリンクライブラリ (DLL) を変更できます。

> [!NOTE]
> このツールは、Visual Studio コマンドプロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。

EDITBIN [コンパイラオプションを使用して](gl-whole-program-optimization.md) 生成されたファイルでは、EDITBIN を使用できません。 /GL を使用して生成されたバイナリファイルに対する変更は、再コンパイルとリンクによって実現される必要があります。

- [EDITBIN コマンド ライン](editbin-command-line.md)

- [EDITBIN オプション](editbin-options.md)

## <a name="see-also"></a>関連項目

[その他の MSVC ビルドツール](c-cpp-build-tools.md)
