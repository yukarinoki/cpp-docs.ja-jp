---
title: CAtlFileMapping クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: 7516349e4ec54d8cb90fa6ff23b0ded954aa043b
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168125"
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
|[CAtlFileMapping:: operator T *](#operator_t_star)|オブジェクトからへの`CAtlFileMapping`暗黙的な`T*`変換を許可します。|

## <a name="remarks"></a>解説

このクラスは、 `CAtlFileMapping`オブジェクトをに暗黙的に`T*`変換できるように、単一のキャスト演算子を追加します。 その他のメンバーは、基本クラス[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)によって提供されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlfile .h

## <a name="catlfilemappingoperator-t"></a><a name="operator_t_star"></a>CAtlFileMapping:: operator T *

オブジェクトからへの`CAtlFileMapping`暗黙的な`T*`変換を許可します。

```cpp
operator T*() const throw();
```

### <a name="return-value"></a>戻り値

メモリマップト`T*`ファイルの先頭へのポインターを返します。

### <a name="remarks"></a>解説

[CAtlFileMappingBase:: GetData](../../atl/reference/catlfilemappingbase-class.md#getdata)を呼び出し、返されたポインターをと`T*`して再解釈します。ここで、 *T*は、このクラスのテンプレートパラメーターとして使用される型です。

## <a name="see-also"></a>関連項目

[CAtlFileMappingBase クラス](../../atl/reference/catlfilemappingbase-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
