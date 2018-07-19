---
title: 共有モード定数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _SH_DENYNO
- _SH_DENYRD
- _SH_DENYRW
- _SH_DENYWR
- _SH_COMPAT
dev_langs:
- C++
helpviewer_keywords:
- _SH_DENYRW constant
- SH_DENYRD constant
- _SH_COMPAT constant
- _SH_DENYRD constant
- SH_DENYRW constant
- sharing constants
- SH_DENYNO constant
- _SH_DENYWR constant
- SH_DENYWR constant
- _SH_DENYNO constant
- SH_COMPAT constant
ms.assetid: 95fadc3a-55dc-473d-98b5-e8211900465d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41060a9dbd3d2bc8176a2b13233db54933a6428b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409704"
---
# <a name="sharing-constants"></a>共有モード定数
ファイル共有モードの定数。  
  
## <a name="syntax"></a>構文  
  
```  
  
#include <share.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 *shflag* 引数で、1 つまたは複数のマニフェスト定数で構成される共有モードを決定します。 これらは、*oflag* 引数と組み合わせて使用できます (「[ファイル定数](../c-runtime-library/file-constants.md)」をご覧ください)。  
  
 次の表に、定数とそれぞれの意味を示します。  
  
|定数|説明|  
|--------------|-------------|  
|`_SH_DENYRW`|ファイルへの読み取りおよび書き込みアクセスを拒否|  
|`_SH_DENYWR`|ファイルへの書き込みアクセスを拒否|  
|`_SH_DENYRD`|ファイルへの読み取りアクセスを拒否|  
|`_SH_DENYNO`|読み取りおよび書き込みアクセスを許可|  
|`_SH_SECURE`|セキュリティで保護されたモードを設定 (共有読み取り、排他的な書き込みアクセス)。|  
  
## <a name="see-also"></a>参照  
 [_sopen、_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)