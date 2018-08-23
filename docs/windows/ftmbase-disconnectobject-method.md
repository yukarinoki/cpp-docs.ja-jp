---
title: Ftmbase::disconnectobject メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
dev_langs:
- C++
helpviewer_keywords:
- DisconnectObject method
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b467162d2f5cc5b04bc43a6d31019eb08e17e750
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595407"
---
# <a name="ftmbasedisconnectobject-method"></a>FtmBase::DisconnectObject メソッド

オブジェクトへのすべての外部接続が強制的に解放します。 オブジェクトのサーバーでは、シャット ダウンする前に、このメソッドのオブジェクトの実装を呼び出します。

## <a name="syntax"></a>構文

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>パラメーター

*dwReserved*  
今後使用するために予約されています。0 にする必要があります。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="requirements"></a>要件

**ヘッダー:** ftm.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[FtmBase クラス](../windows/ftmbase-class.md)