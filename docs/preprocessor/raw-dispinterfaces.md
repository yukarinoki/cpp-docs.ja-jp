---
title: raw_dispinterfaces |Microsoft ドキュメント
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
ms.openlocfilehash: 1f2a0d91d0f0dd3d23886ade75072526e6c895f7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="rawdispinterfaces"></a>raw_dispinterfaces
**C 固有の仕様**  
  
 ディスパッチインターフェイス メソッドおよびプロパティを呼び出すための低レベルのラッパー関数を生成するようにコンパイラに指示**idispatch::invoke**を返すと、`HRESULT`エラー コード。  
  
## <a name="syntax"></a>構文  
  
```  
raw_dispinterfaces  
```  
  
## <a name="remarks"></a>コメント  
 この属性を指定しない場合、高度なラッパーのみが生成され、エラーの場合は C++ 例外がスローされます。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)