---
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
ms.openlocfilehash: 266347de063b4e050cb032aa2d8d74e7934b8081
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328347"
---
# <a name="editbin-reference"></a>EDITBIN リファレンス

マイクロソフト COFF バイナリ ファイル エディタ (エディットビン.EXE) は、共通オブジェクト ファイル形式 (COFF) バイナリ ファイルを変更します。 EDITBIN を使用して、オブジェクト ファイル、実行可能ファイル、およびダイナミック リンク ライブラリ (DLL) を変更できます。

> [!NOTE]
> このツールは、Visual Studio コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。

[/GL](gl-whole-program-optimization.md)コンパイラ オプションで生成されたファイルでは、EDITBIN を使用できません。 /GL で生成されたバイナリ ファイルに対する変更は、再コンパイルとリンクによって行う必要があります。

- [コマンド ラインを編集します。](editbin-command-line.md)

- [エディットビンオプション](editbin-options.md)

## <a name="see-also"></a>関連項目

[その他の MSVC ビルド ツール](c-cpp-build-tools.md)
