---
title: tlbid |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- tlbid
dev_langs:
- C++
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5bd922089bcf189c403a97679a593a985603a12
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446258"
---
# <a name="tlbid"></a>tlbid
**C++ 固有の仕様**  
  
プライマリ タイプ ライブラリ以外のライブラリの読み込みを許可します。  
  
## <a name="syntax"></a>構文  
  
```  
tlbid(number)  
```  
  
### <a name="parameters"></a>パラメーター  
*数*  
`filename` のタイプ ライブラリの番号。  
  
## <a name="remarks"></a>Remarks  
 
複数のタイプ ライブラリを使用してプライマリ タイプ ライブラリ以外のライブラリを読み込むことが可能に 1 つの DLL に組み込まれているかどうかは**tlbid**します。  
  
例えば:  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
上の式は、下の式と同等です。  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)