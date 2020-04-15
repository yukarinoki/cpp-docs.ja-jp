---
title: クラス
ms.date: 10/22/2018
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
ms.openlocfilehash: 66d33d62212389a2b0f318250c1c16a99167c6eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330680"
---
# <a name="csocketaddr-class"></a>クラス

このクラスは、ホスト名をホスト アドレスに変換するメソッドを提供し、IPv4 形式と IPv6 形式の両方をサポートします。

## <a name="syntax"></a>構文

```
class CSocketAddr
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cソケットアダー::Cソケットアダー](#csocketaddr)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cソケットアダー::FindAddr](#findaddr)|指定されたホスト名をホスト アドレスに変換します。|
|[Cソケットアダー::FindINET4Addr](#findinet4addr)|IPv4 ホスト名をホスト アドレスに変換します。|
|[Cソケットアダー::FindINET6Addr](#findinet6addr)|IPv6 ホスト名をホスト アドレスに変換します。|
|[を取得します。](#getaddrinfo)|`addrinfo`リスト内の特定の要素へのポインターを返します。|
|[を使用します。](#getaddrinfolist)|`addrinfo`リストへのポインターを返します。|

## <a name="remarks"></a>解説

このクラスは、Windows ソケット API 関数およびライブラリ内のソケット ラッパーで使用するネットワーク アドレスを検索するための IP バージョンに依存しないアプローチを提供します。

ネットワーク アドレスの検索に使用されるこのクラスのメンバーは、Win32 API 関数[getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo)を使用します。 ANSI または UNICODE のどちらにコードがコンパイルされているかによって、関数の ANSI または UNICODE バージョンが呼び出されます。

このクラスは、IPv4 と IPv6 の両方のネットワーク アドレスをサポートします。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsocket.h

## <a name="csocketaddrcsocketaddr"></a><a name="csocketaddr"></a>Cソケットアダー::Cソケットアダー

コンストラクターです。

```
CSocketAddr();
```

### <a name="remarks"></a>解説

新`CSocketAddr`しいオブジェクトを作成し、ホストに関する応答情報を含むリンク リストを初期化します。

## <a name="csocketaddrfindaddr"></a><a name="findaddr"></a>Cソケットアダー::FindAddr

指定されたホスト名をホスト アドレスに変換します。

```
int FindAddr(
    const TCHAR *szHost,
    const TCHAR *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const TCHAR *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```

### <a name="parameters"></a>パラメーター

*szホスト*<br/>
ホスト名またはドット IP アドレス。

*サービス名*<br/>
ホスト上のサービスのポート番号または名前。

*nポルトノ*<br/>
ポート番号。

*フラグ*<br/>
0 またはAI_PASSIVE、AI_CANONNAME、またはAI_NUMERICHOSTの組み合わせ。

*addr_family*<br/>
アドレス ファミリ (PF_INETなど)。

*sock_type*<br/>
ソケットの種類 (SOCK_STREAMなど)。

*ai_proto*<br/>
プロトコル (IPPROTO_IP、IPPROTO_IPV6など)

### <a name="return-value"></a>戻り値

アドレスが正常に計算された場合は 0 を返します。 エラー発生時に 0 以外の Windows ソケット エラー コードを返します。 成功した場合、計算されたアドレスは、 および を使用して`CSocketAddr::GetAddrInfoList`参照されるリンク`CSocketAddr::GetAddrInfo`リストに格納されます。

### <a name="remarks"></a>解説

ホスト名パラメーターは IPv4 または IPv6 のいずれかの形式で指定できます。 このメソッドは、変換を実行するために Win32 API 関数[getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo)を呼び出します。

## <a name="csocketaddrfindinet4addr"></a><a name="findinet4addr"></a>Cソケットアダー::FindINET4Addr

IPv4 ホスト名をホスト アドレスに変換します。

```
int FindINET4Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>パラメーター

*szホスト*<br/>
ホスト名またはドット IP アドレス。

*nポルトノ*<br/>
ポート番号。

*フラグ*<br/>
0 またはAI_PASSIVE、AI_CANONNAME、またはAI_NUMERICHOSTの組み合わせ。

*sock_type*<br/>
ソケットの種類 (SOCK_STREAMなど)。

### <a name="return-value"></a>戻り値

アドレスが正常に計算された場合は 0 を返します。 エラー発生時に 0 以外の Windows ソケット エラー コードを返します。 成功した場合、計算されたアドレスは、 および を使用して`CSocketAddr::GetAddrInfoList`参照されるリンク`CSocketAddr::GetAddrInfo`リストに格納されます。

### <a name="remarks"></a>解説

このメソッドは、変換を実行するために Win32 API 関数[getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo)を呼び出します。

## <a name="csocketaddrfindinet6addr"></a><a name="findinet6addr"></a>Cソケットアダー::FindINET6Addr

IPv6 ホスト名をホスト アドレスに変換します。

```
int FindINET6Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>パラメーター

*szホスト*<br/>
ホスト名またはドット IP アドレス。

*nポルトノ*<br/>
ポート番号。

*フラグ*<br/>
0 またはAI_PASSIVE、AI_CANONNAME、またはAI_NUMERICHOSTの組み合わせ。

*sock_type*<br/>
ソケットの種類 (SOCK_STREAMなど)。

### <a name="return-value"></a>戻り値

アドレスが正常に計算された場合は 0 を返します。 エラー発生時に 0 以外の Windows ソケット エラー コードを返します。 成功した場合、計算されたアドレスは、 および を使用して`CSocketAddr::GetAddrInfoList`参照されるリンク`CSocketAddr::GetAddrInfo`リストに格納されます。

### <a name="remarks"></a>解説

このメソッドは、変換を実行するために Win32 API 関数[getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo)を呼び出します。

## <a name="csocketaddrgetaddrinfo"></a><a name="getaddrinfo"></a>を取得します。

`addrinfo`リスト内の特定の要素へのポインターを返します。

```
addrinfo* const GetAddrInfo(int nIndex = 0) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[addrinfo](/windows/win32/api/ws2def/ns-ws2def-addrinfow)リスト内の特定の要素への参照。

### <a name="return-value"></a>戻り値

ホストに関する応答`addrinfo`情報を含むリンク リスト内の*nIndex*によって参照される構造体へのポインターを返します。

## <a name="csocketaddrgetaddrinfolist"></a><a name="getaddrinfolist"></a>を使用します。

`addrinfo`リストへのポインターを返します。

```
addrinfo* const GetAddrInfoList() const;
```

### <a name="return-value"></a>戻り値

ホストに関する応答情報を含む`addrinfo`1 つ以上の構造体のリンクリストへのポインター。 詳細については、 [addrinfo 構造体](/windows/win32/api/ws2def/ns-ws2def-addrinfow)を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
