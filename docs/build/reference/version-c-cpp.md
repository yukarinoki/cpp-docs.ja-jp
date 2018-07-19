---
title: バージョン (C/C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VERSION
dev_langs:
- C++
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fcaf4e113af6182a2d3d735e4c668b62336e2c79
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375023"
---
# <a name="version-cc"></a>VERSION (C/C++)
.Exe ファイルのヘッダーに数値を格納するリンクまたは DLL に指示します。  
  
```  
VERSION major[.minor]  
```  
  
## <a name="remarks"></a>コメント  
 *メジャー*と*マイナー*引数には 0 ~ 65,535 の範囲の 10 進数。 既定値は、バージョン 0.0 です。  
  
 バージョン番号を指定するのと同じ方法は、[バージョン情報](../../build/reference/version-version-information.md)(/バージョン) オプション。  
  
## <a name="see-also"></a>関連項目  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)