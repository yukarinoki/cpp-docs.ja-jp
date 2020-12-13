---
description: '詳細情報: CAtlFileMapping クラス'
title: CAtlFileMapping クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: 875979d47ad4cb5b9c59047eff1f50acd35d1251
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147421"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping クラス

このクラスは、 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)のメソッドにキャスト演算子を追加して、メモリマップトファイルを表します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

### <a name="parameters"></a>パラメーター

*T*<br/>
キャスト演算子に使用されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAtlFileMapping:: operator T *](#operator_t_star)|オブジェクトからへの暗黙的な変換 `CAtlFileMapping` を許可 `T*` します。|

## <a name="remarks"></a>解説

このクラスは、オブジェクトをに暗黙的に変換できるように、単一のキャスト演算子を追加し `CAtlFileMapping` `T*` ます。 その他のメンバーは、基本クラス [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)によって提供されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>要件

**ヘッダー:** atlfile .h

## <a name="catlfilemappingoperator-t"></a><a name="operator_t_star"></a> CAtlFileMapping:: operator T *

オブジェクトからへの暗黙的な変換 `CAtlFileMapping` を許可 `T*` します。

```cpp
operator T*() const throw();
```

### <a name="return-value"></a>戻り値

`T*`メモリマップトファイルの先頭へのポインターを返します。

### <a name="remarks"></a>解説

[CAtlFileMappingBase:: GetData](../../atl/reference/catlfilemappingbase-class.md#getdata)を呼び出し、返されたポインターをとして再解釈します。ここで、 `T*` *T* は、このクラスのテンプレートパラメーターとして使用される型です。

## <a name="see-also"></a>関連項目

[CAtlFileMappingBase クラス](../../atl/reference/catlfilemappingbase-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
