---
title: Platform::outofmemoryexception クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::OutOfMemoryException
- VCCORLIB/Platform::OutOfMemoryException::OutOfMemoryException
dev_langs:
- C++
helpviewer_keywords:
- Platform::OutOfMemoryException
ms.assetid: 49c19f6b-f66c-4448-b861-91dcbf32de2c
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f80424026d903127bfd4eb9e29faa0a4001ce938
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33087257"
---
# <a name="platformoutofmemoryexception-class"></a>Platform::OutOfMemoryException クラス
メモリが不足して操作を完了できないときにスローされます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public ref class OutOfMemoryException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、 [COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。  
  
### <a name="requirements"></a>要件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## <a name="see-also"></a>関連項目  
 [Platform::COMException クラス](../cppcx/platform-comexception-class.md)