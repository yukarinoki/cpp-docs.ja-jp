---
title: IColumnsInfoImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
- GetColumnInfo
- ATL::IColumnsInfoImpl::GetColumnInfo
- ATL.IColumnsInfoImpl.GetColumnInfo
- ATL::IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl::GetColumnInfo
- IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl.GetColumnInfo
- IColumnsInfoImpl<T>::MapColumnIDs
- MapColumnIDs
- ATL::IColumnsInfoImpl::MapColumnIDs
- IColumnsInfoImpl.MapColumnIDs
- ATL::IColumnsInfoImpl<T>::MapColumnIDs
- IColumnsInfoImpl::MapColumnIDs
- ATL.IColumnsInfoImpl<T>.MapColumnIDs
- ATL.IColumnsInfoImpl.MapColumnIDs
helpviewer_keywords:
- IColumnsInfoImpl class
- GetColumnInfo method
- MapColumnIDs method
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
ms.openlocfilehash: 67052bdc5d49673146c036167c027d1efd882495
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556505"
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl クラス

実装を提供、 [IColumnsInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms724541(v=vs.85))インターフェイス。

## <a name="syntax"></a>構文

```cpp
template <class T>
class ATL_NO_VTABLE IColumnsInfoImpl :
   public IColumnsInfo, 
   public CDBIDOps
```

### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IColumnsInfoImpl`します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|ほとんどのコンシューマーが必要な列のメタデータを返します。|
|[MapColumnIDs](#mapcolumnids)|指定した列の Id によって識別される行セット内の列の序数の配列を返します。|

## <a name="remarks"></a>Remarks

行セットとコマンドの必須のインターフェイスです。 プロバイダーの動作を変更する`IColumnsInfo`実装では、プロバイダーの列マップを変更する必要があります。

## <a name="getcolumninfo"></a> Icolumnsinfoimpl::getcolumninfo

ほとんどのコンシューマーが必要な列のメタデータを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (GetColumnInfo)(DBORDINAL* pcColumns,
   DBCOLUMNINFO** prgInfo,
   OLECHAR** ppStringsBuffer);
```

#### <a name="parameters"></a>パラメーター

参照してください[icolumnsinfo::getcolumninfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms722704(v=vs.85))で、 *OLE DB プログラマーズ リファレンス*します。

## <a name="mapcolumnids"></a> Icolumnsinfoimpl::mapcolumnids

指定した列の Id によって識別される行セット内の列の序数の配列を返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD (MapColumnIDs)(DBORDINAL cColumnIDs,
   const DBID rgColumnIDs[],
   DBORDINAL rgColumns[]);
```

#### <a name="parameters"></a>パラメーター

参照してください[IColumnsInfo::MapColumnIDs](https://docs.microsoft.com/previous-versions/windows/desktop/ms714200(v=vs.85))で、 *OLE DB プログラマーズ リファレンス*します。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)