---
title: CW2AEX クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 62fd48a34b82e0671d417a882e040a87a7691c01
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363999"
---
# <a name="cw2aex-class"></a>CW2AEX クラス
このクラスは、文字列変換マクロによって使用`CT2AEX`、 `CW2TEX`、 `CW2CTEX`、および`CT2CAEX`、および typedef **CW2A**です。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<int t_nBufferLength = 128>  
class CW2AEX
```  
  
#### <a name="parameters"></a>パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用するバッファーのサイズ。 既定の長さは 128 バイトです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CW2AEX::CW2AEX](#cw2aex)|コンストラクターです。|  
|[CW2AEX:: ~ CW2AEX](#dtor)|デストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CW2AEX::operator LPSTR](#operator_lpstr)|変換演算子です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CW2AEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバーです。|  
|[CW2AEX::m_szBuffer](#m_szbuffer)|静的バッファー、変換後の文字列を格納するために使用します。|  
  
## <a name="remarks"></a>コメント  
 追加の機能が必要な場合を除き、使用`CT2AEX`、 `CW2TEX`、 `CW2CTEX`、 `CT2CAEX`、または**CW2A**コードにします。  
  
 このクラスには、変換の結果を格納するために使用が固定サイズの静的バッファーが含まれています。 結果が大きすぎて静的バッファーに収まらない場合、クラスは `malloc` を使用してメモリを割り当て、オブジェクトがスコープから外れときにそのメモリを解放します。 これにより、テキストとは異なり、ATL のこのクラスは、安全にループで使用して、スタックがオーバーフローするされませんの以前のバージョンで使用できる変換マクロです。  
  
 クラスは、失敗をヒープにメモリを割り当てるしようとするが呼び出されます`AtlThrow`の引数を持つ**E_OUTOFMEMORY**です。  
  
 既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。 特定の変換の動作をオーバーライドする場合は、クラスのコンス トラクターの 2 番目のパラメーターとしてコード ページを指定します。  
  
 次のマクロは、このクラスに基づいています。  
  
- `CT2AEX`  
  
- `CW2TEX`  
  
- `CW2CTEX`  
  
- `CT2CAEX`  
  
 次の typedef は、このクラスに基づいています。  
  
- **CW2A**  
  
 これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL および MFC 文字列変換マクロ](string-conversion-macros.md)です。  
  
## <a name="example"></a>例  
 参照してください[ATL および MFC 文字列変換マクロ](string-conversion-macros.md)をこれらの文字列変換マクロを使用する例についてはします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlconv.h  
  
##  <a name="cw2aex"></a>  CW2AEX::CW2AEX  
 コンストラクターです。  
  
```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2AEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 変換するテキスト文字列。  
  
 `nCodePage`  
 変換を実行するために使用するコード ページです。 Windows SDK 関数のコード ページ パラメーターの説明を参照してください[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)詳細についてはします。  
  
### <a name="remarks"></a>コメント  
 変換プロセスで使用するバッファーを割り当てます。  
  
##  <a name="dtor"></a>  CW2AEX:: ~ CW2AEX  
 デストラクターです。  
  
```
~CW2AEX() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたバッファーを解放します。  
  
##  <a name="m_psz"></a>  CW2AEX::m_psz  
 ソース文字列を格納するデータ メンバーです。  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CW2AEX::m_szBuffer  
 静的バッファー、変換後の文字列を格納するために使用します。  
  
```
char m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>  CW2AEX::operator LPSTR  
 変換演算子です。  
  
```  
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 種類としてテキスト文字列を返す**LPSTR です。**  
  
## <a name="see-also"></a>関連項目  
 [CA2AEX クラス](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
 [CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
 [CW2CWEX クラス](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
