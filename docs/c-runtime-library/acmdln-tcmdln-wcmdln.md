---
title: _acmdln, _tcmdln, _wcmdln | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _wcmdln
- _acmdln
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _acmdln
- acmdln
- _wcmdln
- wcmdln
- _tcmdln
- tcmdln
dev_langs:
- C++
helpviewer_keywords:
- _wcmdln global variable
- wcmdln global variable
- _acmdln global variable
- _tcmdln global variable
- tcmdln global variable
- acmdln global variable
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 141e261af618cc6058a2a731b70e824582be303b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="acmdln-tcmdln-wcmdln"></a>_acmdln, _tcmdln, _wcmdln
内部 CRT グローバル変数。 コマンド ライン。  
  
## <a name="syntax"></a>構文  
  
```  
char * _acmdln;  
wchar_t * _wcmdln;  
  
#ifdef WPRFLAG  
   #define _tcmdln _wcmdln  
#else  
   #define _tcmdln _acmdln  
```  
  
## <a name="remarks"></a>コメント  
 これらの CRT 内部変数には、完全なコマンド ラインが格納されます。 これらは CRT のエクスポートされたシンボルで公開されていますが、コードでの使用が目的ではありません。 `_acmdln` には、データは文字列として格納されます。 `_wcmdln` には、データはワイド文字列として格納されます。 `_tcmdln` は、どちらが適切かに応じて `_acmdln` または`_wcmdln` として定義できます。  
  
## <a name="see-also"></a>参照  
 [グローバル変数](../c-runtime-library/global-variables.md)