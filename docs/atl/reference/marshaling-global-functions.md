---
title: マーシャリング (グローバル関数を)
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
ms.openlocfilehash: 79b19b613fbae49c0f8338dcadd2225e092fb371
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835325"
---
# <a name="marshaling-global-functions"></a>マーシャリング (グローバル関数を)

これらの関数は、マーシャリングデータをインターフェイスポインターにマーシャリングおよび変換するためのサポートを提供します。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。

|名前|説明|
|-|-|
|[AtlFreeMarshalStream](#atlfreemarshalstream)|マーシャリングデータとポインターを解放し `IStream` ます。|
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|新しいストリームオブジェクトを作成し、指定したインターフェイスポインターをマーシャリングします。|
|[AtlUnmarshalPtr](#atlunmarshalptr)|ストリームのマーシャリングデータをインターフェイスポインターに変換します。|

## <a name="requirements"></a>要件:

**ヘッダー:** atlbase. h

## <a name="atlfreemarshalstream"></a><a name="atlfreemarshalstream"></a> AtlFreeMarshalStream

ストリーム内のマーシャリング データを解放し、次にストリーム ポインターも解放します。

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```

### <a name="parameters"></a>パラメーター

*pStream*<br/>
から `IStream` マーシャリングに使用されるストリームのインターフェイスへのポインター。

### <a name="example"></a>例

[AtlMarshalPtrInProc](#atlmarshalptrinproc)の例を参照してください。

## <a name="atlmarshalptrinproc"></a><a name="atlmarshalptrinproc"></a> AtlMarshalPtrInProc

新しいストリーム オブジェクトを作成し、プロキシの CLSID をストリームに書き込みます。さらに、プロキシの初期化に必要なデータをストリームに書き込んで、指定されたインターフェイス ポインターをマーシャリングします。

```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
からマーシャリングするインターフェイスへのポインター。

*iid*<br/>
からマーシャリングされるインターフェイスの GUID。

*ppStream*<br/>
入出力 `IStream` マーシャリングに使用される新しいストリームオブジェクトのインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ポインターを複数のストリームにマーシャリングできるように、MSHLFLAGS_TABLESTRONG フラグが設定されています。 また、ポインターのマーシャリングを複数回行うこともできます。

マーシャリングに失敗した場合は、ストリームポインターが解放されます。

`AtlMarshalPtrInProc` インプロセスオブジェクトへのポインターに対してのみ使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]

## <a name="atlunmarshalptr"></a><a name="atlunmarshalptr"></a> AtlUnmarshalPtr

ストリームのマーシャリング データをクライアントが使用できるインターフェイス ポインターに変換します。

```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```

### <a name="parameters"></a>パラメーター

*pStream*<br/>
からマーシャリング解除されるストリームへのポインター。

*iid*<br/>
からマーシャリング解除されるインターフェイスの GUID。

*ppUnk*<br/>
入出力マーシャリング解除されたインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="example"></a>例

[AtlMarshalPtrInProc](#atlmarshalptrinproc)の例を参照してください。

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
