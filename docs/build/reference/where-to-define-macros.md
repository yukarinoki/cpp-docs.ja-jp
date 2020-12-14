---
description: '詳細情報: マクロを定義する場所'
title: マクロを定義する場所
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: b5fc7d6e1fd8247816993929791bf734596d00e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259202"
---
# <a name="where-to-define-macros"></a>マクロを定義する場所

コマンドライン、コマンドファイル、メイクファイル、または Tools.ini ファイルでマクロを定義します。

メイクファイルまたは Tools.ini ファイルでは、各マクロ定義は個別の行に記述する必要があり、スペースやタブで始めることはできません。等号を囲むスペースやタブは無視されます。 すべての [文字列文字](defining-an-nmake-macro.md) は、前後の引用符と埋め込みスペースを含むリテラルです。

コマンドラインまたはコマンドファイルでは、スペースとタブは引数を区切るため、等号を囲むことはできません。 `string`にスペースまたはタブが埋め込まれている場合は、文字列自体またはマクロ全体を二重引用符 ("") で囲みます。

## <a name="see-also"></a>関連項目

[NMAKE マクロの定義](defining-an-nmake-macro.md)
