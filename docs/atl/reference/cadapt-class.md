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
ms.openlocfilehash: 1bae98663b8dc2b09efeff9139e8d028abcd862e
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168834"
---
# <a name="cadapt-class"></a>CAdapt クラス

このテンプレートは、オブジェクトのアドレス以外の値を返すために、アドレス演算子を再定義するクラスをラップするときに使用されます。

## <a name="syntax"></a>構文

```cpp
template <class T>
class CAdapt
```

### <a name="parameters"></a>パラメーター

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
|[CAdapt:: operator const T&](#operator_const_t_amp)|へ`m_T`の**定数**参照を返します。|
|[CAdapt:: operator T&](#operator_t_amp)|`m_T` への参照を返します。|
|[CAdapt:: operator <](#operator_lt)|適合された型のオブジェクトを `m_T` と比較します。|
|[CAdapt:: operator =](#operator_eq)|適合された型のオブジェクトを `m_T` に割り当てます。|
|[CAdapt:: operator = =](#operator_eq_eq)|適合された型のオブジェクトを `m_T` と比較します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CAdapt:: m_T](#m_t)|適合しているデータ。|

## <a name="remarks"></a>解説

`CAdapt` は、オブジェクトのアドレス以外の値を返すために、アドレス演算子 (`operator &`) を再定義するクラスをラップするときに使用される簡単なテンプレートです。 このようなクラスの例としては、ATL の `CComBSTR`、`CComPtr`、および `CComQIPtr` クラス、そしてコンパイラ COM サポート クラスである `_com_ptr_t` が含まれます。 これらのクラスはすべて、アドレス演算子を再定義して、いずれかのデータメンバー (の`CComBSTR`場合は BSTR) のアドレスと、他のクラスの場合はインターフェイスポインターを返します。

`CAdapt`主な役割は、クラス*T*によって定義されたアドレス演算子を非表示にすることです。ただし、適用されるクラスの特性は維持されます。 `CAdapt`この役割を果たしには、パブリックメンバー、型*t*の[m_T](#m_t)を保持し、変換演算子、比較演算子、およびコピーコンストラクターを定義します。 `CAdapt`これにより、の特殊化を型*t*のオブジェクトとして扱うことができます。

アダプター クラス `CAdapt` は、いくつかの container-style クラスで、含まれるオブジェクトのアドレスを address-of 演算子を使用して取得できることが想定されているために、役立ちます。 address-of 演算子の再定義によって、この要件に混乱が生じ、通常はコンパイル エラーが発生し、"単に動作" することが想定されているクラスで、適合されていない型の使用が妨げられることがあります。 `CAdapt` では、こうした問題を回避するための手段が提供されています。

通常 container-style クラスでは、`CAdapt`、`CComBSTR`、`CComPtr`、または `CComQIPtr` オブジェクトを保存する場合に `_com_ptr_t` を使用します。 これは、C++11 Standard のサポート前には C++ Standard Library コンテナーで最も一般的に必要とされていましたが、C++11 Standard Library コンテナーは `operator&()` をオーバーロードした型と共に自動的に動作します。 標準ライブラリは、 [std:: addressof](../../standard-library/memory-functions.md#addressof)を内部的に使用してオブジェクトの真のアドレスを取得することで、これを実現します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcomcli. h

## <a name="cadaptcadapt"></a><a name="cadapt"></a>CAdapt::CAdapt

コンストラクターを使用すると、アダプターオブジェクトを既定で構築したり、適合する型のオブジェクトからコピーしたり、別のアダプターオブジェクトからコピーしたりすることができます。

```cpp
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*.Rsrc*<br/>
新しく構築されたアダプターオブジェクトにコピーされるように、適合させる型の変数。

*rSrCA*<br/>
新しく構築されたアダプターオブジェクトに、包含データをコピー (または移動) する必要があるアダプターオブジェクト。

## <a name="cadaptm_t"></a><a name="m_t"></a>CAdapt:: m_T

適用されているデータを保持します。

```cpp
T m_T;
```

### <a name="remarks"></a>解説

この**パブリック**データメンバーには、 [operator const t&](#operator_const_t_amp)および[operator t&](#operator_t_amp)を使用して直接または間接的にアクセスできます。

## <a name="cadaptoperator-const-tamp"></a><a name="operator_const_t_amp"></a>CAdapt:: operator const T&amp;

[M_T](#m_t)メンバーへの**定数**参照を返します。これにより、アダプターオブジェクトを*T*型のオブジェクトとして扱うことができます。

```cpp
operator const T&() const;
```

### <a name="return-value"></a>戻り値

へ**const** `m_T`の定数参照。

## <a name="cadaptoperator-tamp"></a><a name="operator_t_amp"></a>CAdapt:: operator T&amp;

[M_T](#m_t)メンバーへの参照を返します。これにより、アダプターオブジェクトを*T*型のオブジェクトとして扱うことができます。

```cpp
operator T&();
```

### <a name="return-value"></a>戻り値

`m_T` への参照です。

## <a name="cadaptoperator-lt"></a><a name="operator_lt"></a>CAdapt:: operator&lt;

適用された型のオブジェクトと[m_T](#m_t)を比較します。

```cpp
bool operator<(const T& rSrc) const;
```

### <a name="parameters"></a>パラメーター

*.Rsrc*<br/>
比較するオブジェクトへの参照。

### <a name="return-value"></a>戻り値

`m_T`と*rsrc*の比較結果。

## <a name="cadaptoperator-"></a><a name="operator_eq"></a>CAdapt:: operator =

代入演算子は、引数*Rsrc*をデータメンバー [m_T](#m_t)に代入し、現在のアダプターオブジェクトを返します。

```cpp
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*.Rsrc*<br/>
コピーされる適用可能な型のオブジェクトへの参照。

*rSrCA*<br/>
移動するオブジェクトへの参照。

### <a name="return-value"></a>戻り値

現在のオブジェクトへの参照。

## <a name="cadaptoperator-"></a><a name="operator_eq_eq"></a>CAdapt:: operator = =

適用された型のオブジェクトと[m_T](#m_t)を比較します。

```cpp
bool operator== (const T& rSrc) const;
```

### <a name="parameters"></a>パラメーター

*.Rsrc*<br/>
比較するオブジェクトへの参照。

### <a name="return-value"></a>戻り値

*M_T*と*rsrc*の比較結果。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
