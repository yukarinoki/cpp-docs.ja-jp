---
title: CFixedStringT クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93125d15be32a95d71c763f476fad700dab65a3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356988"
---
# <a name="cfixedstringt-class"></a>CFixedStringT クラス
このクラスは、固定された文字バッファーを使用して、文字列オブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```  
  
#### <a name="parameters"></a>パラメーター  
 `StringType`  
 固定文字列オブジェクトの基本クラスとして使用でき、いずれかの`CStringT`-型のベースします。 いくつかの例は、 `CString`、 `CStringA`、および`CStringW`です。  
  
 *t_nChars*  
 バッファーに格納されている文字の数。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFixedStringT::CFixedStringT](#cfixedstringt)|文字列オブジェクトのコンス トラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CFixedStringT::operator =](#eq)|新しい値を割り当てます、`CFixedStringT`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 このクラスに基づくカスタム文字列クラスの例は、`CStringT`です。 非常に似ていますが、2 つのクラスは実装が異なります。 主要な違い`CFixedStringT`と`CStringT`は。  
  
-   最初の文字バッファーは、オブジェクトの一部として割り当てられているし、サイズが*t_nChars*です。 これにより、 **CFixedString**パフォーマンス向上のための連続したメモリのチャンクを占有するオブジェクト。 ただし場合の内容、`CFixedStringT`オブジェクトを超えた*t_nChars*バッファーが動的に割り当てられます。  
  
-   文字バッファー、`CFixedStringT`オブジェクトが同じ長さでは常に ( *t_nChars*)。 バッファー サイズに制限はありません`CStringT`オブジェクト。  
  
-   メモリ マネージャー`CFixedStringT`を共有するようにカスタマイズされた、 [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)の 2 つ以上のオブジェクト`CFixedStringT`objectsis が許可されていません。 `CStringT` オブジェクトには、この制限はありません。  
  
 詳細のカスタマイズについて`CFixedStringT`の string オブジェクトのメモリ管理は一般を参照してください、[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** cstringt.h  
  
##  <a name="cfixedstringt"></a>  CFixedStringT::CFixedStringT  
 `CFixedStringT` オブジェクトを構築します。  
  
```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT(const StringType& str);
CFixedStringT(const StringType::XCHAR* psz);
explicit CFixedStringT(const StringType::YCHAR* psz);
explicit CFixedStringT(const unsigned char* psz);
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 これにコピーされる null で終わる文字列`CFixedStringT`オブジェクト。  
  
 `str`  
 既存の`CFixedStringT`オブジェクトにコピーされるこの`CFixedStringT`オブジェクト。  
  
 `pStringMgr`  
 メモリ マネージャーへのポインター、`CFixedStringT`オブジェクト。 詳細については`IAtlStringMgr`およびメモリ管理を`CFixedStringT`を参照してください[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)です。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは、新しい割り当てられている記憶域に入力データをコピーするために注意してくださいメモリ不足の例外が発生する可能性があります。 変換関数として機能するこれらのコンス トラクターの一部に注意してください。  
  
##  <a name="operator__eq"></a>  CFixedStringT::operator =  
 既存の再初期化`CFixedStringT`新しいデータを持つオブジェクト。  
  
```
CFixedStringT<StringType, t_nChars>& operator=(
  const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT<StringType, t_nChars>& operator=(const char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* psz);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& str);
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 これにコピーされる null で終わる文字列`CFixedStringT`オブジェクト。  
  
 `psz`  
 既存の`CFixedStringT`これにコピーされる`CFixedStringT`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 注意すべき、代入演算子を使用すると、新しい記憶域は多くの場合、その結果を保持するために割り当てられているために、例外が発生するメモリ`CFixedStringT`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)




