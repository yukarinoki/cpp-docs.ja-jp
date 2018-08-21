---
title: TerminateMap 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
dev_langs:
- C++
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: de57e03b1e3a150ab96cb72996b48200b153de1c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016708"
---
# <a name="terminatemap-function"></a>TerminateMap 関数
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
### <a name="parameters"></a>パラメーター  
 *モジュール*  
 A[モジュール](../windows/module-class.md)します。  
  
 *サーバー名*  
 パラメーターで指定されたモジュールでクラス ファクトリのサブセットの名前*モジュール*します。  
  
 *forceTerminate*  
 **true**クラスを終了するに関係なく、ファクトリがアクティブです。**false**クラス ファクトリを終了しない場合は、ファクトリがアクティブにします。  
  
## <a name="return-value"></a>戻り値  
 **true**クラス ファクトリをすべてが終了した。 それ以外の場合**false**します。  
  
## <a name="remarks"></a>Remarks  
 指定されたモジュールでクラス ファクトリをシャット ダウンします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)