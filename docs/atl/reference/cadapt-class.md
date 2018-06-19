---
title: CAdapt クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
dev_langs:
- C++
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cabdf0a396f50f548cbe01a765411120ff7dd9f1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365599"
---
# <a name="cadapt-class"></a>CAdapt クラス
このテンプレートは、オブジェクトのアドレス以外の値を返すために、アドレス演算子を再定義するクラスをラップするときに使用されます。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class CAdapt
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 適合された型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAdapt::CAdapt](#cadapt)|コンストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAdapt::operator const T (& a)](#operator_const_t_amp)|`const` への `m_T` 参照を返します。|  
|[CAdapt::operator T (& a)](#operator_t_amp)|`m_T` への参照を返します。|  
|[CAdapt::operator <](#operator_lt)|適合された型のオブジェクトを `m_T` と比較します。|  
|[CAdapt::operator =](#operator_eq)|適合された型のオブジェクトを `m_T` に割り当てます。|  
|[CAdapt::operator = =](#operator_eq_eq)|適合された型のオブジェクトを `m_T` と比較します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAdapt::m_T](#m_t)|適合しているデータ。|  
  
## <a name="remarks"></a>コメント  
 `CAdapt` address-of 演算子を再定義するクラスをラップするために使用する簡単なテンプレートは、( `operator &`) を返すオブジェクトのアドレス以外のものです。 このようなクラスの例としては、ATL の `CComBSTR`、`CComPtr`、および `CComQIPtr` クラス、そしてコンパイラ COM サポート クラスである `_com_ptr_t` が含まれます。 これらのクラスはすべて、いずれかのデータ メンバーのアドレスを返すために address-of 演算子を再定義します (`BSTR` の場合には `CComBSTR`、他のクラスの場合にはインターフェイス ポインター)。  
  
 `CAdapt` の主な役割は、クラス `T` によって定義された address-of 演算子を隠しながら、適合されたクラスの特性を保持することです。 `CAdapt` パブリック メンバーを保持してこのロールを満たす[m_T](#m_t)、型の`T`との特殊化を許可するには、変換演算子、比較演算子、およびコピー コンス トラクターを定義することによって`CAdapt`されるかのように扱われます型のオブジェクト`T`です。  
  
 アダプター クラス `CAdapt` は、いくつかの container-style クラスで、含まれるオブジェクトのアドレスを address-of 演算子を使用して取得できることが想定されているために、役立ちます。 address-of 演算子の再定義によって、この要件に混乱が生じ、通常はコンパイル エラーが発生し、"単に動作" することが想定されているクラスで、適合されていない型の使用が妨げられることがあります。 `CAdapt` では、こうした問題を回避するための手段が提供されています。  
  
 通常 container-style クラスでは、`CAdapt`、`CComBSTR`、`CComPtr`、または `CComQIPtr` オブジェクトを保存する場合に `_com_ptr_t` を使用します。 これは、C++11 Standard のサポート前には C++ Standard Library コンテナーで最も一般的に必要とされていましたが、C++11 Standard Library コンテナーは `operator&()` をオーバーロードした型と共に自動的に動作します。 標準ライブラリでは、これを実現内部的に使用して、 [std::addressof](../../standard-library/memory-functions.md#addressof)オブジェクトの場合は true。 アドレスを取得します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcomcli.h  
  
##  <a name="cadapt"></a>  CAdapt::CAdapt  
 コンス トラクターを使用すると、既定で構築された、適合された型のオブジェクトからコピーまたは別のアダプター オブジェクトからコピーするアダプター オブジェクト。  
  
```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>パラメーター  
 `rSrc`  
 新しく構築されたアダプタ オブジェクトにコピーするのに適合している型の変数です。  
  
 *rSrCA*  
 アダプター オブジェクトが含まれているデータをコピー (または移動する)、新しく構築されたアダプタ オブジェクトにします。  
  
##  <a name="m_t"></a>  CAdapt::m_T  
 適合しているデータを保持します。  
  
```
T m_T;
```  
  
### <a name="remarks"></a>コメント  
 これは、**パブリック**データ メンバーにアクセスできる直接的または間接的に[演算子 const T &](#operator_const_t_amp)と[演算子 T (& a)](#operator_t_amp)です。  
  
##  <a name="operator_const_t_amp"></a>  CAdapt::operator const T&amp;  
 返します、 **const**への参照、 [m_T](#m_t) 、そのアダプタ オブジェクトを型のオブジェクトの場合と同様に扱うことを許可するメンバー`T`です。  
  
```  
operator const T&() const;
```  
  
### <a name="return-value"></a>戻り値  
 A **const**への参照を`m_T`です。  
  
##  <a name="operator_t_amp"></a>  CAdapt::operator T&amp;  
 参照を返します、 [m_T](#m_t) 、そのアダプタ オブジェクトを型のオブジェクトの場合と同様に扱うことを許可するメンバー`T`です。  
  
```  
operator T&();
```     
  
### <a name="return-value"></a>戻り値  
 参照を`m_T`です。  
  
##  <a name="operator_lt"></a>  CAdapt::operator &lt;  
 適合された型のオブジェクトと比較[m_T](#m_t)です。  
  
```
bool operator<(const T& rSrc) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `rSrc`  
 比較するオブジェクトへの参照。  
  
### <a name="return-value"></a>戻り値  
 間の比較の結果`m_T`と`rSrc`です。  
  
##  <a name="operator_eq"></a>  CAdapt::operator =  
 代入演算子は、引数を割り当てます`rSrc`、データ メンバーに[m_T](#m_t)現在のアダプター オブジェクトを返します。  
  
```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>パラメーター  
 `rSrc`  
 コピーされる適合された型のオブジェクトへの参照。 

 `rSrCA` 移動するオブジェクトへの参照。 
  
### <a name="return-value"></a>戻り値  
 現在のオブジェクトへの参照。  
  
##  <a name="operator_eq_eq"></a>  CAdapt::operator = =  
 適合された型のオブジェクトと比較[m_T](#m_t)です。  
  
```
bool operator== (const T& rSrc) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `rSrc`  
 比較するオブジェクトへの参照。  
  
### <a name="return-value"></a>戻り値  
 間の比較の結果`m_T`と`rSrc`です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
