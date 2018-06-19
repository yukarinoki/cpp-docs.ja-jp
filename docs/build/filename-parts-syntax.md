---
title: ファイル名分割構文 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d807087be171a2ad63ed37a8b359c3200c812040
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367486"
---
# <a name="filename-parts-syntax"></a>ファイル名分割構文
コマンド ファイル名分割構文では、(暗黙の依存する場合があります) を最初の依存ファイル名のコンポーネントを表します。 ファイル名コンポーネントは、ファイルのドライブ、パス、基本名、および拡張機能として、指定されたはディスク上に存在していないようです。 使用して **%s**を完全なファイル名を表します。 使用して **%&#124;**[*パーツ*]**F** (垂直バー文字に依存してパーセント記号) をファイル名の部分を表す場所*パーツ*任意の順序で、次の文字の 0 個以上にすることができます。  
  
|文字|説明|  
|------------|-----------------|  
|文字がありません。|完全な名前 (と同じ **%s**)|  
|**d**|ドライブ|  
|**p**|パス|  
|**f**|ファイルのベース名|  
|**e**|ファイル拡張子|  
  
 たとえば、ファイル名は c:\prog.exe とします。  
  
-   %s は c:\prog.exe されます。  
  
-   %&#124;F c:\prog.exe になります  
  
-   %&#124;dF c になります  
  
-   %&#124;pF は c:\ になります  
  
-   %&#124;fF prog になります  
  
-   %&#124;eF exe になります  
  
## <a name="see-also"></a>関連項目  
 [メイクファイルのコマンド](../build/commands-in-a-makefile.md)