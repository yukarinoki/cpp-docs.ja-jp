---
title: Asyncbase::getonprogress メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::GetOnProgress
dev_langs:
- C++
helpviewer_keywords:
- GetOnProgress method
ms.assetid: 286ddc9c-3e30-41a2-8e8b-e53d3fb0649d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fbc3010fa24c315837cc61c5a9361d7f5350a633
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420135"
---
# <a name="asyncbasegetonprogress-method"></a>AsyncBase::GetOnProgress メソッド

指定された変数には、現在の進行状況イベント ハンドラーのアドレスをコピーします。

## <a name="syntax"></a>構文

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>パラメーター

*progressHandler*<br/>
現在の進行状況イベント ハンドラーのアドレスが格納されている場所です。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_ILLEGAL_METHOD_CALL します。

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[AsyncBase クラス](../windows/asyncbase-class.md)