---
title: マクロを定義する where |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29a2899d7dba0b34c0ac3319c253c8056912d883
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713818"
---
# <a name="where-to-define-macros"></a>マクロを定義する場所

コマンドライン、コマンド ファイル、メイクファイルでまたは tools.ini マクロを定義します。

メイクファイルまたは Tools.ini ファイルでは、各マクロ定義が別々 の行に表示する必要があり、スペースまたはタブで始めることはできません。スペースや等号 (=) の周囲のタブは無視されます。 すべて[文字の文字列](../build/defining-an-nmake-macro.md)リテラルを囲む引用符と埋め込み型スペースなどです。

コマンド ファイルまたはコマンドラインで引数を区切るスペースとタブと、等号 (=) で囲むことはできません。 場合`string`スペースまたはタブが埋め込まれて、文字列自体または全体のマクロのいずれかを二重引用符で囲みます ("")。

## <a name="see-also"></a>関連項目

[NMAKE マクロの定義](../build/defining-an-nmake-macro.md)