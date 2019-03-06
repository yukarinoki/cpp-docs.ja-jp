---
title: マクロを定義する場所
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: 5a5e853627f5d337e3f0587cb41fdc77e7eeb4f5
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417919"
---
# <a name="where-to-define-macros"></a>マクロを定義する場所

コマンドライン、コマンド ファイル、メイクファイルでまたは tools.ini マクロを定義します。

メイクファイルまたは Tools.ini ファイルでは、各マクロ定義が別々 の行に表示する必要があり、スペースまたはタブで始めることはできません。スペースや等号 (=) の周囲のタブは無視されます。 すべて[文字の文字列](../build/defining-an-nmake-macro.md)リテラルを囲む引用符と埋め込み型スペースなどです。

コマンド ファイルまたはコマンドラインで引数を区切るスペースとタブと、等号 (=) で囲むことはできません。 場合`string`スペースまたはタブが埋め込まれて、文字列自体または全体のマクロのいずれかを二重引用符で囲みます ("")。

## <a name="see-also"></a>関連項目

[NMAKE マクロの定義](../build/defining-an-nmake-macro.md)
