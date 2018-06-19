---
title: マクロを定義する場所 |Microsoft ドキュメント
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
ms.openlocfilehash: 9cf3e87a50362c770d45f00c4dc17ac3d264f611
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380915"
---
# <a name="where-to-define-macros"></a>マクロを定義する場所
コマンドライン、コマンド ファイル、メイクファイルでも tools.ini マクロを定義します。  
  
 メイクファイルまたは Tools.ini ファイルでは、各マクロ定義は個別の行に表示する必要があり、スペースまたはタブで始めることはできません。スペースや、等号の隣のタブは無視されます。 すべて[文字の文字列](../build/defining-an-nmake-macro.md)リテラルを囲む引用符と埋め込み型スペースなどです。  
  
 コマンドラインまたはコマンド ファイルは、引数を区切るスペースとタブと、等号 (=) を囲むことはできません。 場合`string`スペースまたはタブが埋め込まれる、文字列自体または全体のマクロのいずれかを二重引用符で囲みます ("") です。  
  
## <a name="see-also"></a>関連項目  
 [NMAKE マクロの定義](../build/defining-an-nmake-macro.md)