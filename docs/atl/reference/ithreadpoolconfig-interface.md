---
title: IThreadPoolConfig インターフェイス
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
ms.openlocfilehash: cba82055c292fc966dc2328773cce4aa64d45a64
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835429"
---
# <a name="ithreadpoolconfig-interface"></a>IThreadPoolConfig インターフェイス

このインターフェイスには、スレッドプールを構成するためのメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|名前|説明|
|-|-|
|[GetSize](#getsize)|プール内のスレッドの数を取得するには、このメソッドを呼び出します。|
|[GetTimeout](#gettimeout)|スレッドプールがスレッドのシャットダウンを待機する最大時間 (ミリ秒) を取得するには、このメソッドを呼び出します。|
|[SetSize](#setsize)|プール内のスレッドの数を設定するには、このメソッドを呼び出します。|
|[SetTimeout](#settimeout)|スレッドプールがスレッドのシャットダウンを待機する最大時間をミリ秒単位で設定するには、このメソッドを呼び出します。|

## <a name="remarks"></a>解説

このインターフェイスは、 [CThreadPool](../../atl/reference/cthreadpool-class.md)によって実装されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil. h

## <a name="ithreadpoolconfiggetsize"></a><a name="getsize"></a> IThreadPoolConfig:: GetSize

プール内のスレッドの数を取得するには、このメソッドを呼び出します。

```
STDMETHOD(GetSize)(int* pnNumThreads);
```

### <a name="parameters"></a>パラメーター

*pnNumThreads*<br/>
入出力成功した場合、プール内のスレッドの数を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]

## <a name="ithreadpoolconfiggettimeout"></a><a name="gettimeout"></a> IThreadPoolConfig:: GetTimeout

スレッドプールがスレッドのシャットダウンを待機する最大時間 (ミリ秒) を取得するには、このメソッドを呼び出します。

```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```

### <a name="parameters"></a>パラメーター

*pdwMaxWait*<br/>
入出力成功した場合、スレッドプールがスレッドのシャットダウンを待機する最大時間 (ミリ秒) を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="example"></a>例

「 [Ithreadpoolconfig:: GetSize](#getsize)」を参照してください。

## <a name="ithreadpoolconfigsetsize"></a><a name="setsize"></a> IThreadPoolConfig:: SetSize

プール内のスレッドの数を設定するには、このメソッドを呼び出します。

```
STDMETHOD(SetSize)int nNumThreads);
```

### <a name="parameters"></a>パラメーター

*nNumThreads*<br/>
プール内の要求されたスレッド数。

*Nnumthreads*が負の場合は、スレッドの合計数を取得するために、その絶対値にマシンのプロセッサ数を掛けた値が乗算されます。

*Nnumthreads*が0の場合、ATLS_DEFAULT_THREADSPERPROC には、スレッドの合計数を取得するために、マシン内のプロセッサ数が乗算されます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="example"></a>例

「 [Ithreadpoolconfig:: GetSize](#getsize)」を参照してください。

## <a name="ithreadpoolconfigsettimeout"></a><a name="settimeout"></a> IThreadPoolConfig:: SetTimeout

スレッドプールがスレッドのシャットダウンを待機する最大時間をミリ秒単位で設定するには、このメソッドを呼び出します。

```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```

### <a name="parameters"></a>パラメーター

*dwMaxWait*<br/>
スレッドプールがスレッドのシャットダウンを待機する最大要求時間 (ミリ秒単位)。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="example"></a>例

「 [Ithreadpoolconfig:: GetSize](#getsize)」を参照してください。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/atl-classes.md)<br/>
[CThreadPool クラス](../../atl/reference/cthreadpool-class.md)
