---
title: CComCurrency クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCurrency
- ATLCUR/ATL::CComCurrency
- ATLCUR/ATL::CComCurrency::CComCurrency
- ATLCUR/ATL::CComCurrency::GetCurrencyPtr
- ATLCUR/ATL::CComCurrency::GetFraction
- ATLCUR/ATL::CComCurrency::GetInteger
- ATLCUR/ATL::CComCurrency::Round
- ATLCUR/ATL::CComCurrency::SetFraction
- ATLCUR/ATL::CComCurrency::SetInteger
- ATLCUR/ATL::CComCurrency::m_currency
dev_langs:
- C++
helpviewer_keywords:
- CComCurrency class
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 847cbe230e14975e883c42f52538ba3863d505c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366248"
---
# <a name="ccomcurrency-class"></a>CComCurrency クラス
`CComCurrency` には、CURRENCY オブジェクトを作成および管理するためのメソッドと演算子があります。  
  
## <a name="syntax"></a>構文  
  
```
class CComCurrency
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComCurrency::CComCurrency](#ccomcurrency)|`CComCurrency` オブジェクトのコンストラクター。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComCurrency::GetCurrencyPtr](#getcurrencyptr)|`m_currency` データ メンバーのアドレスを返します。|  
|[Ccomcurrency::getfraction](#getfraction)|`CComCurrency` オブジェクトの小数部を返すには、このメソッドを呼び出します。|  
|[CComCurrency::GetInteger](#getinteger)|`CComCurrency` オブジェクトの整数部を返すには、このメソッドを呼び出します。|  
|[CComCurrency::Round](#round)|`CComCurrency` オブジェクトを最も近い整数値に四捨五入するには、このメソッドを呼び出します。|  
|[CComCurrency::SetFraction](#setfraction)|`CComCurrency` オブジェクトの小数部を設定するには、このメソッドを呼び出します。|  
|[CComCurrency::SetInteger](#setinteger)|`CComCurrency` オブジェクトの整数部を設定するには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComCurrency::operator-](#operator_-)|この演算子は、`CComCurrency` オブジェクトで減算を実行するために使用します。|  
|[CComCurrency::operator! =](#operator_neq)|2 つの `CComCurrency` オブジェクトが等しくないかどうかを比較します。|  
|[CComCurrency::operator *](#operator_star)|この演算子は、`CComCurrency` オブジェクトで乗算を実行するために使用します。|  
|[CComCurrency::operator * =](#operator_star_eq)|この演算子は、`CComCurrency` オブジェクトで乗算を実行し、オブジェクトに結果を代入するために使用します。|  
|[CComCurrency::operator/](#operator_div)|この演算子は、`CComCurrency` オブジェクトで除算を実行するために使用します。|  
|[CComCurrency::operator/=](#operator_div_eq)|この演算子は、`CComCurrency` オブジェクトで除算を実行し、オブジェクトに結果を代入するために使用します。|  
|[CComCurrency::operator +](#operator_add)|この演算子は、`CComCurrency` オブジェクトで加算を実行するために使用します。|  
|[CComCurrency::operator + =](#operator_add_eq)|この演算子は、`CComCurrency` オブジェクトで加算を実行し、結果を現在のオブジェクトに代入するために使用します。|  
|[CComCurrency::operator <](#operator_lt)|この演算子は、2 つの `CComCurrency` オブジェクトを比較して、小さい方を決定します。|  
|[CComCurrency::operator < =](#operator_lt_eq)|この演算子では、2 つの `CComCurrency` オブジェクトを比較して、等しいかどうか、または小さい方を決定します。|  
|[CComCurrency::operator =](#operator_eq)|この演算子は、`CComCurrency` オブジェクトに新しい値を割り当てます。|  
|[CComCurrency::operator =](#operator_-_eq)|この演算子は、`CComCurrency` オブジェクトで減算を実行し、オブジェクトに結果を代入するために使用します。|  
|[CComCurrency::operator = =](#operator_eq_eq)|この演算子は、2 つの `CComCurrency` オブジェクトが等しいかどうかを比較します。|  
|[CComCurrency::operator >](#operator_gt)|この演算子は、2 つの `CComCurrency` オブジェクトを比較して、大きい方を決定します。|  
|[CComCurrency::operator > =](#operator_gt_eq)|この演算子は、2 つの `CComCurrency` オブジェクトを比較して、等しいかどうか、または大きい方を決定します。|  
|[CComCurrency::operator 通貨](#operator_currency)|`CURRENCY` オブジェクトをキャストします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComCurrency::m_currency](#m_currency)|クラス インスタンスによって作成された `CURRENCY` 変数。|  
  
## <a name="remarks"></a>コメント  
 `CComCurrency` 用のラッパーです、**通貨**データ型。 **通貨**10,000 を掛け 2 の補数の 8 バイト整数値として実装されます。 これは、15 桁の整数部と 4 桁の小数部を持つ固定小数点数として表現されます。 **通貨**精度が重要なデータ型は関連する計算、または固定小数点計算は非常に便利です。  
  
 **CComCurrency**ラッパーは、この固定小数点型の算術演算子、代入、および比較の操作を実装します。 固定小数点数の計算中に発生する可能性のある丸め誤差を制御するために、サポートするアプリケーションが選択されています。  
  
 `CComCurrency` オブジェクトは、小数点の左側に値を格納する整数部と小数点の右側に値を格納する小数部という 2 つの構成要素を使用した形で、小数点の左側と右側の数値にアクセスできます。 小数部が-9999 までの整数値として内部に格納されている ( **CY_MIN_FRACTION**) から +9999 ( **CY_MAX_FRACTION**)。 メソッド[ccomcurrency::getfraction](#getfraction) 、係数 10,000 してスケール値を返します ( **CY_SCALE**)。  
  
 整数部と小数部を指定する場合、 **CComCurrency**オブジェクト、小数部が 0 ~ 9999 の範囲の数に注意してください。 これは、小数点の後の有効桁数に 2 桁のみを使用して金額を表す米ドルなどの通貨を扱う場合に重要です。 最後の 2 桁が表示されていない場合でも考慮する必要があります。  
  
|[値]|考えられる CComCurrency の割り当て|  
|-----------|---------------------------------------|  
|$10.50|CComCurrency(10,5000)*または*CComCurrency(10.50)|  
|$10.05|Ccomcurrency (10,500)*または*CComCurrency(10.05)|  
  
 値**CY_MIN_FRACTION**、 **CY_MAX_FRACTION**、および**CY_SCALE** atlcur.h で定義されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcur.h  
  
##  <a name="ccomcurrency"></a>  CComCurrency::CComCurrency  
 コンストラクターです。  
  
```
CComCurrency() throw();
CComCurrency(const CComCurrency& curSrc) throw();
CComCurrency(CURRENCY cySrc) throw();
CComCurrency(DECIMAL dSrc);
CComCurrency(ULONG ulSrc);  
CComCurrency(USHORT usSrc);  
CComCurrency(CHAR cSrc);  
CComCurrency(DOUBLE dSrc);  
CComCurrency(FLOAT fSrc);  
CComCurrency(LONG lSrc);  
CComCurrency(SHORT sSrc);  
CComCurrency(BYTE bSrc);  
CComCurrency(LONGLONG nInteger, SHORT nFraction);  
explicit CComCurrency(LPDISPATCH pDispSrc);  
explicit CComCurrency(const VARIANT& varSrc);  
explicit CComCurrency(LPCWSTR szSrc);  
explicit CComCurrency(LPCSTR szSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `curSrc`  
 既存の `CComCurrency` オブジェクト。  
  
 `cySrc`  
 型の変数**通貨**です。  
  
 `bSrc`、 `dSrc`、 `fSrc`、 `lSrc`、 *sSrc*、 *ulSrc、usSrc*  
 メンバー変数に指定された初期値`m_currency`です。  
  
 `cSrc`  
 メンバー変数に指定された初期値を含む文字`m_currency`です。  
  
 `nInteger`、 *nFraction*  
 整数および通貨の初期値の小数部のコンポーネントです。 参照してください、 [CComCurrency](../../atl/reference/ccomcurrency-class.md)詳細の概要です。  
  
 `pDispSrc`  
 `IDispatch`ポインター。  
  
 *varSrc*  
 型の変数**バリアント**です。 現在のスレッドのロケールを使用して、変換を実行できます。  
  
 `szSrc`  
 初期値を含む Unicode と ANSI 文字列。 現在のスレッドのロケールを使用して、変換を実行できます。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは、設定の初期値[CComCurrency::m_currency](#m_currency)、およびデータ型、整数、文字列、浮動小数点数などの幅広いを受け入れる**通貨**変数、およびその他の`CComCurrency`オブジェクト。 値が指定されていない場合`m_currency`は 0 に設定します。  
  
 オーバーフロー、空の例外指定のないコンス トラクターなど、エラーが発生した場合 ( **throw()**) を呼び出す`AtlThrow`HRESULT エラーを説明するとします。  
  
 浮動小数点または double 値を使用して、値を代入する、なお**CComCurrency(10.50)** は等価**CComCurrency(10,5000)** および not **CComCurrency(10,50)**.  
  
##  <a name="getcurrencyptr"></a>  CComCurrency::GetCurrencyPtr  
 `m_currency` データ メンバーのアドレスを返します。  
  
```
CURRENCY* GetCurrencyPtr() throw();
```  
  
### <a name="return-value"></a>戻り値  
 アドレスを返します、`m_currency`データ メンバー  
  
##  <a name="getfraction"></a>  Ccomcurrency::getfraction  
 小数部を返すには、このメソッドを呼び出して、`CComCurrency`オブジェクト。  
  
```
SHORT GetFraction() const;
```  
  
### <a name="return-value"></a>戻り値  
 小数部を返します、`m_currency`データ メンバーです。  
  
### <a name="remarks"></a>コメント  
 小数部は、-9999 の間の 4 桁の整数値 ( **CY_MIN_FRACTION**) から +9999 ( **CY_MAX_FRACTION**)。 `GetFraction` 10000 この値を返します ( **CY_SCALE**)。 値**CY_MIN_FRACTION**、 **CY_MAX_FRACTION**、および**CY_SCALE** atlcur.h で定義されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]  
  
##  <a name="getinteger"></a>  CComCurrency::GetInteger  
 整数部を取得するには、このメソッドを呼び出して、`CComCurrency`オブジェクト。  
  
```
LONGLONG GetInteger() const;
```  
  
### <a name="return-value"></a>戻り値  
 整数部分を返します、`m_currency`データ メンバーです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]  
  
##  <a name="m_currency"></a>  CComCurrency::m_currency  
 **通貨**データ メンバーです。  
  
```
CURRENCY m_currency;
```  
  
### <a name="remarks"></a>コメント  
 このメンバーは、このクラスのメソッドがアクセスおよび操作の通貨を保持します。  
  
##  <a name="operator_-"></a>  CComCurrency::operator-  
 この演算子は、`CComCurrency` オブジェクトで減算を実行するために使用します。  
  
```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `cur`  
 `CComCurrency` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します、`CComCurrency`減算の結果を表すオブジェクト。 この演算子を呼び出すのオーバーフローなどのエラーが発生した場合`AtlThrow`HRESULT エラーを説明するとします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]  
  
##  <a name="operator_neq"></a>  CComCurrency::operator! =  
 この演算子は、2 つの非等値オブジェクトを比較します。  
  
```
bool operator!= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `cur`  
 比較される `CComCurrency` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**比較対象のアイテムと等しくない場合、`CComCurrency`オブジェクト。 それ以外の場合、 **false**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]  
  
##  <a name="operator_star"></a>  CComCurrency::operator *  
 この演算子は、`CComCurrency` オブジェクトで乗算を実行するために使用します。  
  
```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `nOperand`  
 乗数。  
  
 `cur`  
 `CComCurrency`乗数として使用されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します、`CComCurrency`乗算の結果を表すオブジェクト。 この演算子を呼び出すのオーバーフローなどのエラーが発生した場合`AtlThrow`HRESULT エラーを説明するとします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]  
  
##  <a name="operator_star_eq"></a>  CComCurrency::operator * =  
 この演算子は、`CComCurrency` オブジェクトで乗算を実行し、オブジェクトに結果を代入するために使用します。  
  
```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>パラメーター  
 `nOperand`  
 乗数。  
  
 `cur`  
 `CComCurrency`乗数として使用されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新されたを返します`CComCurrency`オブジェクト。 この演算子を呼び出すのオーバーフローなどのエラーが発生した場合`AtlThrow`HRESULT エラーを説明するとします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]  
  
##  <a name="operator_div"></a>  CComCurrency::operator/  
 この演算子は、`CComCurrency` オブジェクトで除算を実行するために使用します。  
  
```
CComCurrency operator/(long nOperand) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `nOperand`  
 除数。  
  
### <a name="return-value"></a>戻り値  
 返します、`CComCurrency`除算の結果を表すオブジェクト。 除数が 0 の場合、アサーション エラーが発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]  
  
##  <a name="operator_div_eq"></a>  CComCurrency::operator/=  
 この演算子は、`CComCurrency` オブジェクトで除算を実行し、オブジェクトに結果を代入するために使用します。  
  
```
const CComCurrency& operator/= (long nOperand);
```  
  
### <a name="parameters"></a>パラメーター  
 `nOperand`  
 除数。  
  
### <a name="return-value"></a>戻り値  
 更新されたを返します`CComCurrency`オブジェクト。 除数が 0 の場合、アサーション エラーが発生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]  
  
##  <a name="operator_add"></a>  CComCurrency::operator +  
 この演算子は、`CComCurrency` オブジェクトで加算を実行するために使用します。  
  
```
CComCurrency operator+(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `cur`  
 `CComCurrency`元のオブジェクトに追加するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します、`CComCurrency`加算の結果を表すオブジェクト。 この演算子を呼び出すのオーバーフローなどのエラーが発生した場合`AtlThrow`HRESULT エラーを説明するとします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]  
  
##  <a name="operator_add_eq"></a>  CComCurrency::operator + =  
 この演算子は、`CComCurrency` オブジェクトで加算を実行し、結果を現在のオブジェクトに代入するために使用します。  
  
```
const CComCurrency& operator+= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>パラメーター  
 `cur`  
 `CComCurrency` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新されたを返します`CComCurrency`オブジェクト。 この演算子を呼び出すのオーバーフローなどのエラーが発生した場合`AtlThrow`HRESULT エラーを説明するとします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]  
  
##  <a name="operator_lt"></a>  CComCurrency::operator &lt;  
 この演算子は、2 つの `CComCurrency` オブジェクトを比較して、小さい方を決定します。  
  
```
bool operator<(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `cur`  
 `CComCurrency` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**最初のオブジェクトが小さい場合は、2 番目より**false**それ以外の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]  
  
##  <a name="operator_lt_eq"></a>  CComCurrency::operator &lt;=  
 この演算子では、2 つの `CComCurrency` オブジェクトを比較して、等しいかどうか、または小さい方を決定します。  
  
```
bool operator<= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `cur`  
 `CComCurrency` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**最初のオブジェクトが、2 つ目は、以下の場合**false**それ以外の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]  
  
##  <a name="operator_eq"></a>  CComCurrency::operator =  
 この演算子は、`CComCurrency` オブジェクトに新しい値を割り当てます。  
  
```
const CComCurrency& operator= (const CComCurrency& curSrc) throw();
const CComCurrency& operator= (CURRENCY cySrc) throw();
const CComCurrency& operator= (FLOAT fSrc);
const CComCurrency& operator= (SHORT sSrc);
const CComCurrency& operator= (LONG lSrc);
const CComCurrency& operator= (BYTE bSrc);
const CComCurrency& operator= (USHORT usSrc);
const CComCurrency& operator= (DOUBLE dSrc);
const CComCurrency& operator= (CHAR cSrc);
const CComCurrency& operator= (ULONG ulSrc);
const CComCurrency& operator= (DECIMAL dSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `curSrc`  
 A **CComCurrency**オブジェクト。  
  
 `cySrc`  
 型の変数**通貨**です。  
  
 *sSrc*、 `fSrc`、 `lSrc`、 *bSrc*、 *usSrc*、 `dSrc`、 *cSrc*、 *ulSrc*、 `dSrc`  
 代入する数値の値、`CComCurrency`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新されたを返します`CComCurrency`オブジェクト。 この演算子を呼び出すのオーバーフローなどのエラーが発生した場合`AtlThrow`HRESULT エラーを説明するとします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]  
  
##  <a name="operator_-_eq"></a>  CComCurrency::operator =  
 この演算子は、`CComCurrency` オブジェクトで減算を実行し、オブジェクトに結果を代入するために使用します。  
  
```
const CComCurrency& operator-= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>パラメーター  
 `cur`  
 `CComCurrency` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新されたを返します`CComCurrency`オブジェクト。 この演算子を呼び出すのオーバーフローなどのエラーが発生した場合`AtlThrow`HRESULT エラーを説明するとします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]  
  
##  <a name="operator_eq_eq"></a>  CComCurrency::operator = =  
 この演算子は、2 つの `CComCurrency` オブジェクトが等しいかどうかを比較します。  
  
```
bool operator== (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `cur`  
 `CComCurrency`と比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**オブジェクトが等しい場合 (つまり、`m_currency`データ メンバー、両方の整数型と、両方で、小数部からオブジェクトが同じ値を持つ)、 **false**それ以外の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]  
  
##  <a name="operator_gt"></a>  CComCurrency::operator &gt;  
 この演算子は、2 つの `CComCurrency` オブジェクトを比較して、大きい方を決定します。  
  
```
bool operator>(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `cur`  
 `CComCurrency` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**最初のオブジェクトが、2 番目より大きい場合**false**それ以外の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]  
  
##  <a name="operator_gt_eq"></a>  CComCurrency::operator &gt;=  
 この演算子は、2 つの `CComCurrency` オブジェクトを比較して、等しいかどうか、または大きい方を決定します。  
  
```
bool operator>= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `cur`  
 `CComCurrency` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合は、最初のオブジェクトは、2 番目以上**false**それ以外の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]  
  
##  <a name="operator_currency"></a>  CComCurrency::operator 通貨  
 これらの演算子を使用してキャストを`CComCurrency`オブジェクトを**通貨**データ型。  
  
```  
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 参照を返します、**通貨**オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]  
  
##  <a name="round"></a>  CComCurrency::Round  
 通貨の指定した小数点数に丸めるには、このメソッドを呼び出します。  
  
```
HRESULT Roundint nDecimals);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDecimals*  
 これにある数字の数`m_currency`0 ~ 4 の範囲内で、丸められます。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]  
  
##  <a name="setfraction"></a>  CComCurrency::SetFraction  
 `CComCurrency` オブジェクトの小数部を設定するには、このメソッドを呼び出します。  
  
```
HRESULT SetFraction(SHORT nFraction);
```  
  
### <a name="parameters"></a>パラメーター  
 *nFraction*  
 小数部に割り当てられる値、`m_currency`データ メンバーです。 小数部の成分の符号を整数コンポーネントと同じ必要があります、値は、-9999 の範囲内である必要があります ( **CY_MIN_FRACTION**) +9999 ( **CY_MAX_FRACTION**)。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]  
  
##  <a name="setinteger"></a>  CComCurrency::SetInteger  
 `CComCurrency` オブジェクトの整数部を設定するには、このメソッドを呼び出します。  
  
```
HRESULT SetInteger(LONGLONG nInteger);
```  
  
### <a name="parameters"></a>パラメーター  
 `nInteger`  
 整数部に割り当てられる値、`m_currency`データ メンバーです。 整数成分の符号は、既存の小数部の符号と一致する必要があります。  
  
 `nInteger` 範囲である必要があります**CY_MIN_INTEGER**に**CY_MAX_INTEGER**包括的です。 これらの値は、atlcur.h で定義されます。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [COleCurrency クラス](../../mfc/reference/colecurrency-class.md)   
 [通貨](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)   
 [クラスの概要](../../atl/atl-class-overview.md)
