---
title: 依存ファイルのパスを検索 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 577fc7e44bfff35cf7efdcff20dc4cdca1c7001e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380486"
---
# <a name="search-paths-for-dependents"></a>依存ファイルの検索パス
各依存ファイルには、次のように指定された、省略可能な検索パスがあります。  
  
## <a name="syntax"></a>構文  
  
```  
{directory[;directory...]}dependent  
```  
  
## <a name="remarks"></a>コメント  
 (Nmake の) は、現在のディレクトリでは、最初にし、指定された順序内のディレクトリで依存関係を検索します。 マクロには、検索パスの一部またはすべてを指定できます。 ディレクトリ名を囲む中かっこ ({});複数のディレクトリをセミコロン (;) で区切ります。 スペースまたはタブは許可されません。  
  
## <a name="see-also"></a>関連項目  
 [依存](../build/dependents.md)