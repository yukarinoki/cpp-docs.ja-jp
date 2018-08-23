---
title: Comptr::asiid メソッド |Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: d5a3cdb2-796d-4410-966a-847c0e8fb226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d79707eaa3e5e93ab5c05e120d1556ee86168af2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607299"
---
# <a name="comptrasiid-method"></a>ComPtr::AsIID メソッド

返します、 **ComPtr**指定したインターフェイス ID で識別されるインターフェイスを表すオブジェクトを

## <a name="syntax"></a>構文

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>パラメーター

*riid*  
インターフェイス ID。

*p*  
オブジェクトのインターフェイス ID を持つと等しい場合*riid*で指定されたインターフェイスを二重間接ポインター、 *riid*パラメーター、それ以外へのポインター`IUnknown`します。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[ComPtr クラス](../windows/comptr-class.md)