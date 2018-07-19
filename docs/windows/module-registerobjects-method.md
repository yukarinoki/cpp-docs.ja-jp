---
title: Module::registerobjects メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterObjects
dev_langs:
- C++
helpviewer_keywords:
- RegisterObjects method
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 986dcfff49529eedd8d495f4c37e19fa2b6cb8bc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875345"
---
# <a name="moduleregisterobjects-method"></a>Module::RegisterObjects メソッド
他のアプリケーションがそれらに接続できるように、COM または Windows ランタイム オブジェクトを登録します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `module`  
 COM または Windows ランタイムのオブジェクトの配列。  
  
 `serverName`  
 オブジェクトを作成したサーバーの名前です。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、原因を示す HRESULT 操作に失敗しました。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
## <a name="see-also"></a>関連項目
[Module クラス](../windows/module-class.md)