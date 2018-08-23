---
title: Comptr::releaseandgetaddressof メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3efdce7cde39431a8d6f097aace2ed2f5a66b4d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589948"
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf メソッド

これに関連付けられているインターフェイスを解放**ComPtr**しのアドレスを取得し、 [ptr _](../windows/comptr-ptr-data-member.md)データ メンバーは、リリースされたインターフェイスへのポインターが含まれています。

## <a name="syntax"></a>構文

```cpp
T** ReleaseAndGetAddressOf();
```

## <a name="return-value"></a>戻り値

アドレス、 [ptr _](../windows/comptr-ptr-data-member.md)データ メンバー **ComPtr**します。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[ComPtr クラス](../windows/comptr-class.md)  
[ComPtr::ptr_ データ メンバー](../windows/comptr-ptr-data-member.md)