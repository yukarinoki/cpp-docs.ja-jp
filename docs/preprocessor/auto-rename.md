---
title: auto_rename |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- auto_rename
dev_langs:
- C++
helpviewer_keywords:
- auto_rename attribute
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28e55b9afd3a6254182f1bb0a94fb2136d036c32
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413498"
---
# <a name="autorename"></a>auto_rename
**C++ 固有の仕様**  
  
潜在的な名前の競合を解決するため、変数名に 2 つのアンダースコア (__) を追加して C++ の予約語の名前を変更します。  
  
## <a name="syntax"></a>構文  
  
```  
auto_rename  
```  
  
## <a name="remarks"></a>Remarks 

この属性は、変数名として C++ の予約語 (キーワードまたはマクロ) を使用しているタイプ ライブラリをインポートするときに使用します。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目 

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)