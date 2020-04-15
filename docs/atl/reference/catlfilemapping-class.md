---
title: クラスを指定します。
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: ca46ccdacf5ea24f1de26cdc75bf808c4ecfaa40
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318959"
---
# <a name="catlfilemapping-class"></a>クラスを指定します。

このクラスは[、CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)のメソッドにキャスト演算子を追加する、メモリ マップト ファイルを表します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
キャスト演算子に使用されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[カトルファイルマッピング::演算子T*](#operator_t_star)|オブジェクトを`CAtlFileMapping`に暗黙的に`T*`変換できます。|

## <a name="remarks"></a>解説

このクラスは、オブジェクトを に暗黙的に変換できるように`CAtlFileMapping`、単`T*`一のキャスト演算子を追加します。 その他のメンバーは、基本クラス[である CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)によって提供されます。

## <a name="inheritance-hierarchy"></a>継承階層

[カトルファイルマッピングベース](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlfile.h

## <a name="catlfilemappingoperator-t"></a><a name="operator_t_star"></a>カトルファイルマッピング::演算子T*

オブジェクトを`CAtlFileMapping`に暗黙的に`T*`変換できます。

```
operator T*() const throw();
```

### <a name="return-value"></a>戻り値

メモリ`T*`マップト ファイルの先頭へのポインターを返します。

### <a name="remarks"></a>解説

[CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata)を呼び出し、返されたポインター`T*`を、このクラスのテンプレート パラメーターとして使用される*型である場所*として再解釈します。

## <a name="see-also"></a>関連項目

[クラスを指定します。](../../atl/reference/catlfilemappingbase-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
