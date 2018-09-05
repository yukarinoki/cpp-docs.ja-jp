---
title: Platform::idisposable インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
dev_langs:
- C++
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3899c25d71ad08cc058280271080c19d11222ed
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751009"
---
# <a name="platformidisposable-interface"></a>Platform::IDisposable インターフェイス
アンマネージ リソースを解放するために使用されます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public interface class IDisposable  
```  
  
## <a name="attributes"></a>属性  
 **GuidAttribute**("de0cbaea-8065-4a45-b196-c9d443f9bab3")  
  
 **VersionAttribute**(NTDDI_WIN8)  
  
### <a name="members"></a>メンバー  
 IDisposable インターフェイスは IUnknown インターフェイスから継承します。 また IDisposable には次の種類のメンバーもあります。  
  
 **メソッド**  
  
 IDisposable インターフェイスには、次のメソッドがあります。  
  
|メソッド|説明|  
|------------|-----------------|  
|Dispose|アンマネージ リソースを解放するために使用されます。|  
  
### <a name="requirements"></a>要件  
 **クライアントがサポートされている最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform