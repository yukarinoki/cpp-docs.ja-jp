---
title: マクロを定義する場所
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: 130863f8c5640a0c4915734732d93fc00d3d6479
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656249"
---
# <a name="where-to-define-macros"></a>マクロを定義する場所

コマンドライン、コマンド ファイル、メイクファイルでまたは tools.ini マクロを定義します。

メイクファイルまたは Tools.ini ファイルでは、各マクロ定義が別々 の行に表示する必要があり、スペースまたはタブで始めることはできません。スペースや等号 (=) の周囲のタブは無視されます。 すべて[文字の文字列](../build/defining-an-nmake-macro.md)リテラルを囲む引用符と埋め込み型スペースなどです。

コマンド ファイルまたはコマンドラインで引数を区切るスペースとタブと、等号 (=) で囲むことはできません。 場合`string`スペースまたはタブが埋め込まれて、文字列自体または全体のマクロのいずれかを二重引用符で囲みます ("")。

## <a name="see-also"></a>関連項目

[NMAKE マクロの定義](../build/defining-an-nmake-macro.md)