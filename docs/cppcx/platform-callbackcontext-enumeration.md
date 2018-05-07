---
title: Platform::callbackcontext 列挙 |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 757de5f686bb809a5d2fb159a3ee547a20edc982
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext 列挙型
コールバック関数 (イベント ハンドラー) が実行するスレッド コンテキストを指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum class CallbackContext {};  
```  
  
### <a name="members"></a>メンバー  
  
|型コード|説明|  
|---------------|-----------------|  
|どれでも可|コールバック関数は、任意のスレッド コンテキストで実行できます。|  
|同|コールバック関数は、非同期操作を開始したスレッド コンテキストでのみ実行できます。|  
  
### <a name="requirements"></a>要件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd