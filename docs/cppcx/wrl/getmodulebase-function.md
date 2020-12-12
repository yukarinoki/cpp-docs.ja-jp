---
description: '詳細情報: GetModuleBase 関数'
title: GetModuleBase 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: cdedaf905da194400209840b6bd84fa8e626eb0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295199"
---
# <a name="getmodulebase-function"></a>GetModuleBase 関数

[RuntimeClass](runtimeclass-class.md)オブジェクトの参照カウントをインクリメントおよびデクリメントできる[modulebase](modulebase-class.md)ポインターを取得します。

## <a name="syntax"></a>構文

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>戻り値

`ModuleBase` オブジェクトを指すポインターです。

## <a name="remarks"></a>解説

この関数は、オブジェクト参照カウントをインクリメントおよびデクリメントするために、内部的に使用されます。

この関数を使用すると、 [modulebase:: IncrementObjectCount](modulebase-class.md#incrementobjectcount) と [modulebase::D ecrementobjectcount](modulebase-class.md#decrementobjectcount)を呼び出すことにより、参照カウントを制御できます。

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
