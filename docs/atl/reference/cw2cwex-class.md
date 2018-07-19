---
title: CW2CWEX クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f97ddd87194d9cf7cce0b5fcd898b6a9f391d908
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879382"
---
# <a name="cw2cwex-class"></a>CW2CWEX クラス
このクラスは、文字列変換マクロ CW2CTEX と CT2CWEX、typedef CW2W によって使用されます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<int t_nBufferLength = 128>  
class CW2CWEX
```  
  
#### <a name="parameters"></a>パラメーター  
 *t_nBufferLength*  
 変換プロセスで使用されるバッファーのサイズ。 既定の長さは 128 バイトです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CW2CWEX::CW2CWEX](#cw2cwex)|コンストラクターです。|  
|[CW2CWEX:: ~ CW2CWEX](#dtor)|デストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CW2CWEX::operator LPCWSTR](#operator_lpcwstr)|変換演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CW2CWEX::m_psz](#m_psz)|ソース文字列が格納されるデータ メンバー。|  
  
## <a name="remarks"></a>Remarks  
 追加の機能が必要な場合を除き、CW2CTEX、CT2CWEX、または CW2W をコードで使用します。  
  
 このクラスは、安全にループ内で使用し、スタック オーバーフローが発生しません。 既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。  
  
 次のマクロは、このクラスに基づいています。  
  
- CW2CTEX  
  
- CT2CWEX  
  
 次の typedef は、このクラスに基づいています。  
  
- CW2W  
  
 これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL と MFC 文字列変換マクロ](string-conversion-macros.md)します。  
  
## <a name="example"></a>例  
 参照してください[ATL と MFC 文字列変換マクロ](string-conversion-macros.md)のこれらの文字列変換マクロの使用例についてはします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlconv.h  
  
##  <a name="cw2cwex"></a>  CW2CWEX::CW2CWEX  
 コンストラクターです。  
  
```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2CWEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *2 つ*  
 変換するテキスト文字列。  
  
 *nCodePage*  
 コード ページです。 このクラスでは使用されません。  
  
### <a name="remarks"></a>Remarks  
 変換プロセスで使用されるバッファーを割り当てます。  
  
##  <a name="dtor"></a>  CW2CWEX:: ~ CW2CWEX  
 デストラクターです。  
  
```
~CW2CWEX() throw();
```  
  
### <a name="remarks"></a>Remarks  
 割り当てられたバッファーを解放します。  
  
##  <a name="m_psz"></a>  CW2CWEX::m_psz  
 ソース文字列が格納されるデータ メンバー。  
  
```
LPCWSTR m_psz;
```  
  
##  <a name="operator_lpcwstr"></a>  CW2CWEX::operator LPCWSTR  
 変換演算子。  
  
```  
operator LPCWSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 LPCWSTR を入力すると、テキスト文字列を返します。  
  
## <a name="see-also"></a>関連項目  
 [CA2AEX クラス](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
 [CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
 [CW2AEX クラス](../../atl/reference/cw2aex-class.md)   
 [CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
