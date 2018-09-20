---
title: rename_namespace |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7608255b5369443ce1045f896b776cb283fdb1cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411860"
---
# <a name="renamenamespace"></a>rename_namespace
**C++ 固有の仕様**  
  
タイプ ライブラリの内容を含む名前空間の名前を変更します。  
  
## <a name="syntax"></a>構文  
  
```  
rename_namespace("NewName")  
```  
  
### <a name="parameters"></a>パラメーター  
*NewName*  
名前空間の新しい名前。  
  
## <a name="remarks"></a>Remarks  
 
1 つの引数を受け取る*NewName*、新しい名前空間の名前を指定します。  
  
名前空間を削除するには、使用、 [no_namespace](../preprocessor/no-namespace.md)属性の代わりにします。  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 
[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)