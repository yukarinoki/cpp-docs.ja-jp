---
title: スタブ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STUB
dev_langs:
- C++
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 385e073f877a938a3b73fa79036d27cf50c1e4ec
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375202"
---
# <a name="stub"></a>STUB
仮想デバイス ドライバー (VxD) を構築するモジュール定義ファイルで使用されているときにすることができます (WINNT で定義されている IMAGE_DOS_HEADER 構造体を含むファイル名を指定します。H) をクリックし、既定のヘッダーではなく、仮想デバイス ドライバー (VxD) で使用します。  
  
```  
STUB:filename  
```  
  
## <a name="remarks"></a>コメント  
 同等の方法を指定する*filename*では、 [/stub](../../build/reference/stub-ms-dos-stub-file-name.md)リンカー オプション。  
  
 スタブは VxD を構築するときにのみ、モジュール定義ファイルで有効です。  
  
## <a name="see-also"></a>関連項目  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)