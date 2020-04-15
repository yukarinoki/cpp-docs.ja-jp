---
title: CAdapt クラス
ms.date: 11/04/2016
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
ms.openlocfilehash: 23544bc103de0d7b76cd73d403626ba93af6e31a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321641"
---
# <a name="cadapt-class"></a>CAdapt クラス

このテンプレートは、オブジェクトのアドレス以外の値を返すために、アドレス演算子を再定義するクラスをラップするときに使用されます。

## <a name="syntax"></a>構文

```
template <class T>
class CAdapt
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
適合された型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAdapt::CAdapt](#cadapt)|コンストラクターです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAdapt::演算子コンスト T&](#operator_const_t_amp)|への**const**参照`m_T`を返します。|
|[CAdapt::演算子T&](#operator_t_amp)|`m_T` への参照を返します。|
|[CAdapt::演算子<](#operator_lt)|適合された型のオブジェクトを `m_T` と比較します。|
|[CAdapt::演算子 =](#operator_eq)|適合された型のオブジェクトを `m_T` に割り当てます。|
|[CAdapt::演算子 ==](#operator_eq_eq)|適合された型のオブジェクトを `m_T` と比較します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CAdapt::m_T](#m_t)|適合しているデータ。|

## <a name="remarks"></a>解説

`CAdapt` は、オブジェクトのアドレス以外の値を返すために、アドレス演算子 (`operator &`) を再定義するクラスをラップするときに使用される簡単なテンプレートです。 このようなクラスの例としては、ATL の `CComBSTR`、`CComPtr`、および `CComQIPtr` クラス、そしてコンパイラ COM サポート クラスである `_com_ptr_t` が含まれます。 これらのクラスはすべて、address-of 演算子を再定義して、データ メンバーの 1 つのアドレス (BSTR`CComBSTR`の場合は BSTR、他のクラスの場合はインターフェイス ポインタ) を返します。

`CAdapt`' の主な役割は、クラス*T*で定義された address-of 演算子を非表示にすることですが、適合クラスの特性はそのまま保持されます。 `CAdapt`この役割を果たす[には、](#m_t) *m_T型*T を保持し、 変換演算子、比較演算子、およびコピー コンストラクターを定義して、 の`CAdapt`特殊化を*T*型のオブジェクトとして扱うことができます。

アダプター クラス `CAdapt` は、いくつかの container-style クラスで、含まれるオブジェクトのアドレスを address-of 演算子を使用して取得できることが想定されているために、役立ちます。 address-of 演算子の再定義によって、この要件に混乱が生じ、通常はコンパイル エラーが発生し、"単に動作" することが想定されているクラスで、適合されていない型の使用が妨げられることがあります。 `CAdapt` では、こうした問題を回避するための手段が提供されています。

通常 container-style クラスでは、`CAdapt`、`CComBSTR`、`CComPtr`、または `CComQIPtr` オブジェクトを保存する場合に `_com_ptr_t` を使用します。 これは、C++11 Standard のサポート前には C++ Standard Library コンテナーで最も一般的に必要とされていましたが、C++11 Standard Library コンテナーは `operator&()` をオーバーロードした型と共に自動的に動作します。 標準ライブラリは、内部的に[std::addressof](../../standard-library/memory-functions.md#addressof)を使用してオブジェクトの真のアドレスを取得することで、これを実現します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcomcli.h

## <a name="cadaptcadapt"></a><a name="cadapt"></a>CAdapt::CAdapt

コンストラクターを使用すると、アダプター オブジェクトを既定で構築したり、適合型のオブジェクトからコピーしたり、別のアダプタ オブジェクトからコピーしたりできます。

```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*rSrc*<br/>
新しく構築されたアダプタ オブジェクトにコピーされる、変換対象の型の変数。

*ルスルカ*<br/>
含まれるデータを新しく構築されたアダプター・オブジェクトにコピー (または移動) するアダプター・オブジェクト。

## <a name="cadaptm_t"></a><a name="m_t"></a>CAdapt::m_T

適合するデータを保持します。

```
T m_T;
```

### <a name="remarks"></a>解説

この**パブリック**データ メンバーは[、演算子 const T&](#operator_const_t_amp)および[演算子 T ](#operator_t_amp)&を使用して、直接または間接的にアクセスできます。

## <a name="cadaptoperator-const-tamp"></a><a name="operator_const_t_amp"></a>CAdapt::演算子コンストT&amp;

[m_T](#m_t)メンバーへの**const**参照を返し、アダプター オブジェクトが*T*型のオブジェクトであるかのように扱われるようにします。

```
operator const T&() const;
```

### <a name="return-value"></a>戻り値

**への const** `m_T`参照。

## <a name="cadaptoperator-tamp"></a><a name="operator_t_amp"></a>CAdapt::演算子 T&amp;

[m_T](#m_t)メンバーへの参照を返し、アダプター オブジェクトが*型 T*のオブジェクトであるかのように扱うことを許可します。

```
operator T&();
```

### <a name="return-value"></a>戻り値

`m_T` への参照です。

## <a name="cadaptoperator-lt"></a><a name="operator_lt"></a>CAdapt::演算子&lt;

適合型のオブジェクトを[m_T](#m_t)と比較します。

```
bool operator<(const T& rSrc) const;
```

### <a name="parameters"></a>パラメーター

*rSrc*<br/>
比較するオブジェクトへの参照。

### <a name="return-value"></a>戻り値

`m_T` *rSrc*との比較の結果です。

## <a name="cadaptoperator-"></a><a name="operator_eq"></a>CAdapt::演算子 =

代入演算子は、引数*rSrc*をデータ メンバー [m_T](#m_t)に代入し、現在のアダプタ オブジェクトを返します。

```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*rSrc*<br/>
コピーされる適合型のオブジェクトへの参照。

*ルスルカ*<br/>
移動するオブジェクトへの参照。

### <a name="return-value"></a>戻り値

現在のオブジェクトへの参照。

## <a name="cadaptoperator-"></a><a name="operator_eq_eq"></a>CAdapt::演算子 ==

適合型のオブジェクトを[m_T](#m_t)と比較します。

```
bool operator== (const T& rSrc) const;
```

### <a name="parameters"></a>パラメーター

*rSrc*<br/>
比較するオブジェクトへの参照。

### <a name="return-value"></a>戻り値

*m_T*と*rSrc*の比較の結果です。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
