---
title: Comptr::operator&amp;演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f513ac83e0ee83109f42cf87b80b4fcc4960db1f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598604"
---
# <a name="comptroperatoramp-operator"></a>Comptr::operator&amp;演算子

これに関連付けられているインターフェイスを解放**ComPtr**オブジェクトし、のアドレスを取得し、 **ComPtr**オブジェクト。

## <a name="syntax"></a>構文

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

## <a name="return-value"></a>戻り値

現在の弱い参照を**ComPtr**します。

## <a name="remarks"></a>Remarks

このメソッドが異なる[comptr::getaddressof](../windows/comptr-getaddressof-method.md)ことで、このメソッドは、インターフェイス ポインターへの参照を解放します。 使用`ComPtr::GetAddressOf`インターフェイス ポインターのアドレスが必要ですが、そのインターフェイスを解放したくないです。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[ComPtr クラス](../windows/comptr-class.md)