---
title: CSocketAddr クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
dev_langs:
- C++
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 830b1087d0a4792b449c516ed12ad7e8a84b2a51
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363397"
---
# <a name="csocketaddr-class"></a>CSocketAddr クラス
このクラスは、ホスト アドレス、IPv4 と IPV6 の両方の形式をサポートするホスト名を変換するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CSocketAddr
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSocketAddr::CSocketAddr](#csocketaddr)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSocketAddr::FindAddr](#findaddr)|ホスト アドレスに指定されたホスト名を変換するには、このメソッドを呼び出します。|  
|[CSocketAddr::FindINET4Addr](#findinet4addr)|ホスト アドレスを IPv4 ホスト名を変換するには、このメソッドを呼び出します。|  
|[CSocketAddr::FindINET6Addr](#findinet6addr)|ホスト アドレス、IPv6 ホスト名を変換するには、このメソッドを呼び出します。|  
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|特定の要素にポインターを返すには、このメソッドを呼び出す、 **addrinfo**  ボックスの一覧です。|  
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|ポインターを返すには、このメソッドを呼び出す、 **addrinfo**  ボックスの一覧です。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、IP のバージョンが Windows で使用するネットワーク アドレスを検索するための柔軟なアプローチ ソケット API 関数やライブラリのソケット ラッパーを提供します。  
  
 ネットワーク アドレスの検索に使用されるこのクラスのメンバーは、Win32 API 関数を使用して[getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520)です。  
  
 このクラスは、両方の IPv4 と Ipv6 ネットワーク アドレスをサポートします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsocket.h  
  
##  <a name="csocketaddr"></a>  CSocketAddr::CSocketAddr  
 コンストラクターです。  
  
```
CSocketAddr();
```  
  
### <a name="remarks"></a>コメント  
 新たに作成`CSocketAddr`オブジェクトし、ホストの応答情報を含むリンク リストを初期化します。  
  
##  <a name="findaddr"></a>  CSocketAddr::FindAddr  
 ホスト アドレスに指定されたホスト名を変換するには、このメソッドを呼び出します。  
  
```
int FindAddr(
    const char *szHost,
    const char *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const char *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```  
  
### <a name="parameters"></a>パラメーター  
 `szHost`  
 ホスト名または IP アドレスが点線で示されます。  
  
 *szPortOrServiceName*  
 ポート番号またはホスト上のサービスの名前。  
  
 `nPortNo`  
 ポート番号。  
  
 `flags`  
 0 または AI_PASSIVE、AI_CANONNAME または AI_NUMERICHOST の組み合わせ。  
  
 *addr_family*  
 アドレス ファミリ (PF_INET) など。  
  
 `sock_type`  
 ソケットの種類 (SOCK_STREAM) などです。  
  
 *ai_proto*  
 (移植 IPPROTO_IPV6 など) のプロトコルです。  
  
### <a name="return-value"></a>戻り値  
 アドレスが正常に計算される場合は、0 を返します。 0 以外の Windows ソケット エラー コードを返します。 かどうかは成功すると、計算されるアドレスは、格納を使用して参照されているリンクされたリストに`CSocketAddr::GetAddrInfoList`と`CSocketAddr::GetAddrInfo`です。  
  
### <a name="remarks"></a>コメント  
 IPv4 または IPv6 のいずれかの形式で、ホスト名パラメーターがあります。 このメソッドは、Win32 API 関数を呼び出します[getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520)変換を実行します。  
  
##  <a name="findinet4addr"></a>  CSocketAddr::FindINET4Addr  
 ホスト アドレスを IPv4 ホスト名を変換するには、このメソッドを呼び出します。  
  
```
int FindINET4Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>パラメーター  
 `szHost`  
 ホスト名または IP アドレスが点線で示されます。  
  
 `nPortNo`  
 ポート番号。  
  
 `flags`  
 0 または AI_PASSIVE、AI_CANONNAME または AI_NUMERICHOST の組み合わせ。  
  
 `sock_type`  
 ソケットの種類 (SOCK_STREAM) などです。  
  
### <a name="return-value"></a>戻り値  
 アドレスが正常に計算される場合は、0 を返します。 0 以外の Windows ソケット エラー コードを返します。 かどうかは成功すると、計算されるアドレスは、格納を使用して参照されているリンクされたリストに`CSocketAddr::GetAddrInfoList`と`CSocketAddr::GetAddrInfo`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Win32 API 関数を呼び出します[getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520)変換を実行します。  
  
##  <a name="findinet6addr"></a>  CSocketAddr::FindINET6Addr  
 ホスト アドレス、IPv6 ホスト名を変換するには、このメソッドを呼び出します。  
  
```
int FindINET6Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>パラメーター  
 `szHost`  
 ホスト名または IP アドレスが点線で示されます。  
  
 `nPortNo`  
 ポート番号。  
  
 `flags`  
 0 または AI_PASSIVE、AI_CANONNAME または AI_NUMERICHOST の組み合わせ。  
  
 `sock_type`  
 ソケットの種類 (SOCK_STREAM) などです。  
  
### <a name="return-value"></a>戻り値  
 アドレスが正常に計算される場合は、0 を返します。 0 以外の Windows ソケット エラー コードを返します。 かどうかは成功すると、計算されるアドレスは、格納を使用して参照されているリンクされたリストに`CSocketAddr::GetAddrInfoList`と`CSocketAddr::GetAddrInfo`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Win32 API 関数を呼び出します[getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520)変換を実行します。  
  
##  <a name="getaddrinfo"></a>  CSocketAddr::GetAddrInfo  
 特定の要素にポインターを返すには、このメソッドを呼び出す、 **addrinfo**  ボックスの一覧です。  
  
```
addrinfo* const GetAddrInfoint nIndex = 0) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 内の特定の要素への参照、 [addrinfo](http://msdn.microsoft.com/library/windows/desktop/ms737530)  ボックスの一覧です。  
  
### <a name="return-value"></a>戻り値  
 ポインターを返します、 **addrinfo**によって参照される構造`nIndex`ホストに関する応答情報を含むリンク リストです。  
  
##  <a name="getaddrinfolist"></a>  CSocketAddr::GetAddrInfoList  
 ポインターを返すには、このメソッドを呼び出す、 **addrinfo**  ボックスの一覧です。  
  
```
addrinfo* const GetAddrInfoList() const;
```  
  
### <a name="return-value"></a>戻り値  
 1 つまたは複数のリンク リストへのポインター`addrinfo`ホストの応答情報を含む構造体。 詳細については、次を参照してください。 [addrinfo 構造](https://msdn.microsoft.com/library/windows/desktop/ms737530)です。
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
