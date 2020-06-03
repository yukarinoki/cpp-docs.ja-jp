---
title: インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
ms.openlocfilehash: e4b90534fa89ef2aeffe4cd682d92efc16452487
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326357"
---
# <a name="ithreadpoolconfig-interface"></a>インターフェイス

このインターフェイスには、スレッド プールを構成するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[GetSize](#getsize)|プール内のスレッドの数を取得します。|
|[タイムアウトを取得します。](#gettimeout)|スレッド プールがスレッドのシャットダウンを待機する最大時間 (ミリ秒単位) を取得します。|
|[セットサイズ](#setsize)|プール内のスレッドの数を設定します。|
|[Settimeout](#settimeout)|スレッド プールがスレッドのシャットダウンを待機する最大時間をミリ秒単位で設定します。|

## <a name="remarks"></a>解説

このインターフェイスは[、CThreadPool](../../atl/reference/cthreadpool-class.md)によって実装されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="ithreadpoolconfiggetsize"></a><a name="getsize"></a>を設定します。

プール内のスレッドの数を取得します。

```
STDMETHOD(GetSize)(int* pnNumThreads);
```

### <a name="parameters"></a>パラメーター

*スレッド*<br/>
[アウト]成功時にプール内のスレッド数を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]

## <a name="ithreadpoolconfiggettimeout"></a><a name="gettimeout"></a>を設定します。

スレッド プールがスレッドのシャットダウンを待機する最大時間 (ミリ秒単位) を取得します。

```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```

### <a name="parameters"></a>パラメーター

*を待つ*<br/>
[アウト]成功時にスレッド プールがスレッドのシャットダウンを待機する最大時間 (ミリ秒単位) を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="example"></a>例

を参照してください[。](#getsize)

## <a name="ithreadpoolconfigsetsize"></a><a name="setsize"></a>を設定します。

プール内のスレッドの数を設定します。

```
STDMETHOD(SetSize)int nNumThreads);
```

### <a name="parameters"></a>パラメーター

*nNumスレッド*<br/>
プール内の要求されたスレッド数。

*nNumThreads*が負の値の場合、その絶対値は、スレッドの合計数を取得するコンピューター内のプロセッサの数を乗算します。

*nNumThreads*が 0 の場合、ATLS_DEFAULT_THREADSPERPROCは、スレッドの合計数を取得するコンピューター内のプロセッサの数を乗算されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="example"></a>例

を参照してください[。](#getsize)

## <a name="ithreadpoolconfigsettimeout"></a><a name="settimeout"></a>を設定します。

スレッド プールがスレッドのシャットダウンを待機する最大時間をミリ秒単位で設定します。

```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```

### <a name="parameters"></a>パラメーター

*を待つ*<br/>
スレッド プールがスレッドのシャットダウンを待機する要求された最大時間 (ミリ秒単位)。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="example"></a>例

を参照してください[。](#getsize)

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/atl-classes.md)<br/>
[クラス](../../atl/reference/cthreadpool-class.md)
