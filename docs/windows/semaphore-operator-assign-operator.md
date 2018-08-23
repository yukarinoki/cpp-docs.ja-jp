---
title: Semaphore::operator = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: ea19839f-91f0-4b00-a35b-5728fcba4981
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fbce88be7f7b83c22964438bc4ea7a783754fb63
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609009"
---
# <a name="semaphoreoperator-operator"></a>Semaphore::operator= 演算子

指定したハンドルの移動、**セマフォ**現在オブジェクト**セマフォ**オブジェクト。

## <a name="syntax"></a>構文

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>パラメーター

*h*  
右辺値参照を**セマフォ**オブジェクト。

## <a name="return-value"></a>戻り値

現在への参照を**セマフォ**オブジェクト。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目
[Semaphore クラス](../windows/semaphore-class.md)