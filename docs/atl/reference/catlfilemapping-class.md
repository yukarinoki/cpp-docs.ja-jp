---
title: CAtlFileMapping クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ccbf3221bddf39c8069e20636c2f2a1deb597866
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116465"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping クラス

このクラスのメソッドへのキャスト演算子の追加メモリ マップト ファイルを表します[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
キャスト演算子を使用するデータの型。

## <a name="members"></a>メンバー

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAtlFileMapping::operator T *](#operator_t_star)|暗黙的な変換は、`CAtlFileMapping`オブジェクトを`T*`します。|

## <a name="remarks"></a>Remarks

このクラスの暗黙的な変換を許可する 1 つのキャスト演算子を追加します`CAtlFileMapping`オブジェクトを`T*`します。 他のメンバーは、基本クラスによって提供される[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>要件

**ヘッダー:** atlfile.h

##  <a name="operator_t_star"></a>  CAtlFileMapping::operator T *

暗黙的な変換は、`CAtlFileMapping`オブジェクトを`T*`します。

```
operator T*() const throw();
```

### <a name="return-value"></a>戻り値

返します、`T*`メモリ マップト ファイルの先頭へのポインター。

### <a name="remarks"></a>Remarks

呼び出し[CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata)として返されたポインターとして再解釈と、`T*`場所*T*はこのクラスのテンプレート パラメーターとして使用される型です。

## <a name="see-also"></a>関連項目

[CAtlFileMappingBase クラス](../../atl/reference/catlfilemappingbase-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
