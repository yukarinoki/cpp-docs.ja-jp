---
title: グローバル関数のマーシャリング
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
ms.openlocfilehash: b839e93b6251a09ce79df60a49b4054d1af76cc9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326261"
---
# <a name="marshaling-global-functions"></a>グローバル関数のマーシャリング

これらの関数は、マーシャリングデータをインターフェイス ポインタにマーシャリングおよび変換するためのサポートを提供します。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

|||
|-|-|
|[AtlFreeMarshalStream](#atlfreemarshalstream)|マーシャリング データとポインタを`IStream`解放します。|
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|新しいストリーム オブジェクトを作成し、指定したインターフェイス ポインターをマーシャリングします。|
|[AtlUnmarshalPtr](#atlunmarshalptr)|ストリームのマーシャリング データをインターフェイス ポインターに変換します。|

## <a name="requirements"></a>要件:

**ヘッダー:** atlbase.h

## <a name="atlfreemarshalstream"></a><a name="atlfreemarshalstream"></a>アトルフリーマーシャルストリーム

ストリーム内のマーシャリング データを解放し、次にストリーム ポインターも解放します。

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```

### <a name="parameters"></a>パラメーター

*pストリーム*<br/>
[in]マーシャリングに使用される`IStream`ストリームのインターフェイスへのポインター。

### <a name="example"></a>例

「」の例[AtlMarshalPtrInProc](#atlmarshalptrinproc)を参照してください。

## <a name="atlmarshalptrinproc"></a><a name="atlmarshalptrinproc"></a>アトルマーシャルプットリング

新しいストリーム オブジェクトを作成し、プロキシの CLSID をストリームに書き込みます。さらに、プロキシの初期化に必要なデータをストリームに書き込んで、指定されたインターフェイス ポインターをマーシャリングします。

```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
[in]マーシャリングするインターフェイスへのポインター。

*Iid*<br/>
[in]マーシャリングされるインターフェイスの GUID。

*ppStream*<br/>
[アウト]マーシャリングに使用される`IStream`新しいストリーム オブジェクトのインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

MSHLFLAGS_TABLESTRONG フラグは、ポインターを複数のストリームにマーシャリングできるように設定されます。 ポインターは、複数回マーシャリング解除することもできます。

マーシャリングが失敗した場合、ストリーム ポインターは解放されます。

`AtlMarshalPtrInProc`は、インプロセス オブジェクトへのポインターでのみ使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]

## <a name="atlunmarshalptr"></a><a name="atlunmarshalptr"></a>アトルアンマーシャルプター

ストリームのマーシャリング データをクライアントが使用できるインターフェイス ポインターに変換します。

```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```

### <a name="parameters"></a>パラメーター

*pストリーム*<br/>
[in]マーシャリング解除されるストリームへのポインター。

*Iid*<br/>
[in]マーシャリング解除されるインターフェイスの GUID。

*ppUnk*<br/>
[アウト]マーシャリングされていないインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="example"></a>例

「」の例[AtlMarshalPtrInProc](#atlmarshalptrinproc)を参照してください。

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
