---
title: Platform::accessdeniedexception クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4be26bfc87be55d36954429c64094cabd6a6cf9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="platformaccessdeniedexception-class"></a>Platform::AccessDeniedException クラス
リソースや機能へのアクセスが拒否されるとスローされます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable  
```  
  
### <a name="remarks"></a>コメント  
 この例外にヒットした場合は、適切な機能を要求したこと、およびアプリのパッケージ マニフェストで必要な宣言を行ったことを確認します。 詳細については、「 [COMException](../cppcx/platform-comexception-class.md) 」クラスを参照してください。  
  
### <a name="requirements"></a>要件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## <a name="see-also"></a>関連項目  
 [Platform::COMException クラス](../cppcx/platform-comexception-class.md)