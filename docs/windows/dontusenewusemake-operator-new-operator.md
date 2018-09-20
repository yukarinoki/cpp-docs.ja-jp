---
title: Dontusenewusemake::operator new 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs:
- C++
helpviewer_keywords:
- operator new operator
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99e82de06f64816521c47c78648108a9ae815279
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443229"
---
# <a name="dontusenewusemakeoperator-new-operator"></a>DontUseNewUseMake::operator new 演算子

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>パラメーター

*_ _unnamed0*<br/>
割り当てるメモリのバイト数を指定する名前のないパラメーター。

*placement*<br/>
割り当てられる型。

## <a name="return-value"></a>戻り値

演算子をオーバー ロードする場合は、追加の引数を渡す方法を提供します**新しい**します。

## <a name="remarks"></a>Remarks

演算子をオーバー ロード**新しい**しで使用されていることを防ぎます`RuntimeClass`します。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[DontUseNewUseMake クラス](../windows/dontusenewusemake-class.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)