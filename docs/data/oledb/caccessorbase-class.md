---
title: CAccessorBase クラス
ms.date: 11/04/2016
f1_keywords:
- CAccessorBase
- CAccessorBase.Close
- CAccessorBase::Close
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
- CAccessorBase::GetNumAccessors
- GetNumAccessors
- CAccessorBase.GetNumAccessors
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
- CAccessorBase::ReleaseAccessors
- CAccessorBase.ReleaseAccessors
- ReleaseAccessors
helpviewer_keywords:
- CAccessorBase class
- Close method
- GetHAccessor method
- GetNumAccessors method
- IsAutoAccessor method
- ReleaseAccessors method
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
ms.openlocfilehash: eff7eff855bcccefee7e051c67d583d28e488293
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843301"
---
# <a name="caccessorbase-class"></a>CAccessorBase クラス

OLE DB テンプレート内のすべてのアクセサーは、このクラスから派生します。 `CAccessorBase` 1つの行セットで複数のアクセサーを管理できます。 また、パラメーターと出力列の両方のバインドも提供します。

## <a name="syntax"></a>構文

```cpp
// Replace with syntax
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|--|--|
| [閉じる](#close) | アクセサーを閉じます。 |
| [GetHAccessor](#geth) | アクセサーハンドルを取得します。 |
| [GetNumAccessors](#getnum) | クラスによって作成されたアクセサーの数を取得します。 |
| [IsAutoAccessor](#isauto) | 指定されたアクセサーが autoaccessor であるかどうかをテストします。 |
| [ReleaseAccessors](#release) | アクセサーを解放します。 |

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="caccessorbaseclose"></a><a name="close"></a> CAccessorBase:: Close

アクセサーを閉じます。

### <a name="syntax"></a>構文

```cpp
void Close();
```

### <a name="remarks"></a>解説

最初に [Releaseaccessors](../../data/oledb/caccessorbase-releaseaccessors.md) を呼び出す必要があります。

## <a name="caccessorbasegethaccessor"></a><a name="geth"></a> CAccessorBase:: GetHAccessor

指定したアクセサーのアクセサーハンドルを取得します。

### <a name="syntax"></a>構文

```cpp
HACCESSOR GetHAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>パラメーター

*nAccessor*<br/>
からアクセサーのゼロオフセット番号。

### <a name="return-value"></a>戻り値

アクセサーハンドル。

## <a name="caccessorbasegetnumaccessors"></a><a name="getnum"></a> CAccessorBase:: GetNumAccessors

クラスによって作成されたアクセサーの数を取得します。

### <a name="syntax"></a>構文

```cpp
ULONG GetNumAccessors() const;
```

### <a name="return-value"></a>戻り値

クラスによって作成されたアクセサーの数。

## <a name="caccessorbaseisautoaccessor"></a><a name="isauto"></a> CAccessorBase:: IsAutoAccessor

移動操作中にアクセサーに対してデータが自動的に取得される場合は true を返します。

### <a name="syntax"></a>構文

```cpp
bool IsAutoAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>パラメーター

*nAccessor*<br/>
からアクセサーのゼロオフセット番号。

### <a name="return-value"></a>戻り値

**`true`** アクセサーが autoaccessor の場合はを返します。 それ以外の場合はを返し **`false`** ます。

## <a name="caccessorbasereleaseaccessors"></a><a name="release"></a> CAccessorBase:: ReleaseAccessors

クラスによって作成されたアクセサーを解放します。

### <a name="syntax"></a>構文

```cpp
HRESULT ReleaseAccessors(IUnknown* pUnk);
```

#### <a name="parameters"></a>パラメーター

*パンク*<br/>
から `IUnknown` アクセサーが作成された COM オブジェクトのインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

[CAccessorRowset:: Close](../../data/oledb/caccessorrowset-close.md)から呼び出されます。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessorBase クラス](../../data/oledb/caccessorbase-class.md)
