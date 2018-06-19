---
title: CA2AEX クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2AEX
- ATLCONV/ATL::CA2AEX
- ATLCONV/ATL::CA2AEX::CA2AEX
- ATLCONV/ATL::CA2AEX::m_psz
- ATLCONV/ATL::CA2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CA2AEX class
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdbdebb1ab79ceab44a408fc182b6037f2d32fae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358447"
---
# <a name="ca2aex-class"></a>CA2AEX クラス
このクラスは、文字列変換マクロによって使用`CA2TEX`と`CT2AEX`、および typedef **CA2A**です。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <int t_nBufferLength = 128>
class CA2AEX
```  
  
#### <a name="parameters"></a>パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用するバッファーのサイズ。 既定の長さは 128 バイトです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CA2AEX::CA2AEX](#ca2aex)|コンストラクターです。|  
|[CA2AEX:: ~ CA2AEX](#dtor)|デストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CA2AEX::operator LPSTR](#operator_lpstr)|変換演算子です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CA2AEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバーです。|  
|[CA2AEX::m_szBuffer](#m_szbuffer)|静的バッファー、変換後の文字列を格納するために使用します。|  
  
## <a name="remarks"></a>コメント  
 追加の機能が必要な場合を除き、使用`CA2TEX`、 `CT2AEX`、または**CA2A**自分のコード。  
  
 このクラスには、変換の結果を格納するために使用が固定サイズの静的バッファーが含まれています。 結果が大きすぎて静的バッファーに収まらない場合、クラスは `malloc` を使用してメモリを割り当て、オブジェクトがスコープから外れときにそのメモリを解放します。 これにより、テキストとは異なり、ATL のこのクラスは、安全にループで使用して、スタックがオーバーフローするされませんの以前のバージョンで使用できる変換マクロです。  
  
 クラスは、失敗をヒープにメモリを割り当てるしようとするが呼び出されます`AtlThrow`の引数を持つ**E_OUTOFMEMORY**です。  
  
 既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。  
  
 次のマクロは、このクラスに基づいています。  
  
- `CA2TEX`  
  
- `CT2AEX`  
  
 次の typedef は、このクラスに基づいています。  
  
- **CA2A**  
  
 これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL および MFC 文字列変換マクロ](string-conversion-macros.md)です。  
  
## <a name="example"></a>例  
 参照してください[ATL および MFC 文字列変換マクロ](string-conversion-macros.md)をこれらの文字列変換マクロを使用する例についてはします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlconv.h  
  
##  <a name="ca2aex"></a>  CA2AEX::CA2AEX  
 コンストラクターです。  
  
```
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 変換するテキスト文字列。  
  
 `nCodePage`  
 このクラスでは使用しません。  
  
### <a name="remarks"></a>コメント  
 変換に必要なバッファーを作成します。  
  
##  <a name="dtor"></a>  CA2AEX:: ~ CA2AEX  
 デストラクターです。  
  
```
~CA2AEX() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたバッファーを解放します。  
  
##  <a name="m_psz"></a>  CA2AEX::m_psz  
 ソース文字列を格納するデータ メンバーです。  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CA2AEX::m_szBuffer  
 静的バッファー、変換後の文字列を格納するために使用します。  
  
```
char m_szBuffer[ t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>  CA2AEX::operator LPSTR  
 変換演算子です。  
  
```
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 種類としてテキスト文字列を返す**LPSTR**です。  
  
## <a name="see-also"></a>関連項目  
 [CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
 [CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
 [CW2AEX クラス](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)