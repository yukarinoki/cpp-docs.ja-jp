---
title: lock クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs:
- C++
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a860f79b740e0f34eef33b7a96e0236835f1f6b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="lock-class"></a>lock クラス
このクラスは、複数のスレッドからオブジェクトへのアクセスを同期するロックの取得を自動化します。  構築時にロックを取得し、リリースを破棄時ロックします。  
  
## <a name="syntax"></a>構文  
  
```  
ref class lock;  
```  
  
## <a name="remarks"></a>コメント  
 `lock` CLR オブジェクトに対してのみ使用できますが、CLR コードでのみ使用できます。  
  
 ロックのクラスは内部的には、<xref:System.Threading.Monitor>アクセスを同期するためにします。 同期の詳細については、このトピックを参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー ファイル** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>関連項目  
 [lock](../dotnet/lock.md)   
 [lock のメンバー](../dotnet/lock-members.md)