---
title: inject_statement |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb3bdc2b4e00cd9e2167adeb0ad7d3023af9eb2e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384209"
---
# <a name="injectstatement"></a>inject_statement
**C++ 固有の仕様**  
  
タイプ ライブラリ ヘッダーに引数をソース テキストとして挿入します。  
  
## <a name="syntax"></a>構文  
  
```  
inject_statement("source_text")  
```  
  
### <a name="parameters"></a>パラメーター  
*source_text*  
タイプ ライブラリ ヘッダー ファイルに挿入するソース テキスト。  
  
## <a name="remarks"></a>Remarks  
 
テキストは、ヘッダー ファイルのタイプ ライブラリの内容をラップする名前空間宣言の先頭に配置されます。  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)