---
title: raw_dispinterfaces |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_dispinterfaces
dev_langs:
- C++
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02133e6b9d884fa8e0a175dd01845035ec8b96a7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435949"
---
# <a name="rawdispinterfaces"></a>raw_dispinterfaces
**C++ 固有の仕様**  
  
ディスパッチインターフェイス メソッドおよびプロパティを呼び出すための低レベルのラッパー関数を生成するようにコンパイラに指示`IDispatch::Invoke`し HRESULT エラー コードを返します。  
  
## <a name="syntax"></a>構文  
  
```  
raw_dispinterfaces  
```  
  
## <a name="remarks"></a>Remarks  
 
この属性を指定しない場合、高度なラッパーのみが生成され、エラーの場合は C++ 例外がスローされます。  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)