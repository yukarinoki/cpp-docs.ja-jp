---
title: ファイル定数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _O_EXCL
- _O_RDWR
- _O_APPEND
- _O_RDONLY
- _O_TRUNC
- _O_CREAT
- _O_WRONLY
dev_langs:
- C++
helpviewer_keywords:
- _O_RDWR constant
- O_EXCL constant
- O_RDWR constant
- O_WRONLY constant
- O_APPEND constant
- O_CREAT constant
- _O_CREAT constant
- _O_APPEND constant
- _O_EXCL constant
- O_TRUNC constant
- _O_RDONLY constant
- _O_TRUNC constant
- O_RDONLY constant
- _O_WRONLY constant
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31d6deadb3d7cae7ed8717056b632cd46fa79370
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389716"
---
# <a name="file-constants"></a>ファイル定数
## <a name="syntax"></a>構文  
  
```  
  
#include <fcntl.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 以下の 1 つまたは複数の定数で形成される整数式によって、許可される読み取りまたは書き込みの操作の種類が決定されます。 これは、1 つまたは複数の定数と、変換モードの定数を組み合わせることによって形成されます。  
  
 ファイル定数は次のとおりです。  
  
 `_O_APPEND`  
 書き込み操作の前に、ファイル ポインターの位置をファイルの終端に変更します。  
  
 `_O_CREAT`  
 書き込み用の新しいファイルを作成して開きます。*filename* で指定されたファイルが存在する場合は、効果がありません。  
  
 `_O_EXCL`  
 *filename* で指定されたファイルが存在する場合は、エラー値を返します。 `_O_CREAT` と共に使用された場合にのみ適用されます。  
  
 `_O_RDONLY`  
 読み取り専用のファイルを開きます。このフラグを指定すると、`_O_RDWR` と `_O_WRONLY` は指定できません。  
  
 `_O_RDWR`  
 読み取りと書き込み両方のファイルを開きます。このフラグを指定すると、`_O_RDONLY` と `_O_WRONLY` は指定できません。  
  
 `_O_TRUNC`  
 既存のファイルを開き、長さをゼロに切り詰めます。ファイルに書き込みアクセス許可が必要です。 ファイルの内容は破棄されます。 このフラグを指定すると、`_O_RDONLY` は指定できません。  
  
 `_O_WRONLY`  
 書き込み専用のファイルを開きます。このフラグを指定すると、`_O_RDONLY` と `_O_RDWR` は指定できません。  
  
## <a name="see-also"></a>参照  
 [_open、_wopen](../c-runtime-library/reference/open-wopen.md)   
 [_sopen、_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)