---
title: Microsoft::WRL::Wrappers::Details 名前空間
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details
- internal/Microsoft::WRL::Details
- async/Microsoft::WRL::Details
- corewrappers/Microsoft::WRL::Wrappers::Details
- client/Microsoft::WRL::Details
- module/Microsoft::WRL::Details
- event/Microsoft::WRL::Details
helpviewer_keywords:
- Details namespace
ms.assetid: 6d3f04ac-9b53-4a82-a188-a85309ec34a4
ms.openlocfilehash: 005fa79d413708f630b0a6aebbc06782086c81b3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213760"
---
# <a name="microsoftwrlwrappersdetails-namespace"></a>Microsoft::WRL::Wrappers::Details 名前空間

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
namespace Microsoft::WRL::Wrappers::Details;
```

## <a name="members"></a>メンバー

### <a name="classes"></a>クラス

|Name|説明|
|----------|-----------------|
|[SyncLockT クラス](synclockt-class.md)|リソースの排他的な所有権を取得できる型を表します。|
|[SyncLockWithStatusT クラス](synclockwithstatust-class.md)|リソースの排他的な所有権を取得できる型を表します。|

### <a name="methods"></a>メソッド

|Name|説明|
|----------|-----------------|
|[CompareStringOrdinal メソッド](comparestringordinal-method.md)|指定した2つの `HSTRING` オブジェクトを比較し、それらの相対位置を並べ替え順序で示す整数を返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper::D etails

## <a name="see-also"></a>参照

[Microsoft::WRL::Wrappers 名前空間](microsoft-wrl-wrappers-namespace.md)
