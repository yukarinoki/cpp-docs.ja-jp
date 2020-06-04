---
title: runtime_exception クラス
ms.date: 03/27/2019
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
ms.openlocfilehash: ff54357055d373db98f469b071edc75fce75e0b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336792"
---
# <a name="runtime_exception-class"></a>runtime_exception クラス

C++ Accelerated Massive Parallelism (AMP) ライブラリ内の例外の基本型。

### <a name="syntax"></a>構文

```cpp
class runtime_exception : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[runtime_exceptionコンストラクタ](#ctor)|`runtime_exception` クラスの新しいインスタンスを初期化します。|
|[~runtime_exceptionデストラクタ](#dtor)|`runtime_exception` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get_error_code](#get_error_code)|例外の原因となったエラー コードを返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[演算子=](#operator_eq)|指定された `runtime_exception` オブジェクトの内容をこのオブジェクトにコピーします。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`runtime_exception`

## <a name="requirements"></a>必要条件

**ヘッダー:** アンパート.h

**名前空間:** Concurrency

## <a name="runtime_exception-constructor"></a><a name="ctor"></a>runtime_exceptionコンストラクタ

クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```cpp
runtime_exception(
    const char * _Message,
    HRESULT _Hresult ) throw();

explicit runtime_exception(
    HRESULT _Hresult ) throw();

runtime_exception(
    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
この例外の原因になったエラーの説明。

*_Hresult*<br/>
この例外の原因になったエラーの HRESULT。

*_Other*<br/>
コピーする `runtime_exception` オブジェクトです。

### <a name="return-value"></a>戻り値

`runtime_exception` オブジェクトです。

## <a name="runtime_exception-destructor"></a><a name="dtor"></a>~runtime_exceptionデストラクタ

オブジェクトを破棄します。

### <a name="syntax"></a>構文

```cpp
virtual ~runtime_exception() throw();
```

## <a name="get_error_code"></a><a name="get_error_code"></a>get_error_code

例外の原因となったエラー コードを返します。

### <a name="syntax"></a>構文

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>戻り値

この例外の原因になったエラーの HRESULT。

## <a name="operator"></a><a name="operator_eq"></a>演算子=

指定された `runtime_exception` オブジェクトの内容をこのオブジェクトにコピーします。

### <a name="syntax"></a>構文

```cpp
runtime_exception & operator= (    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>パラメーター

*_Other*<br/>
コピーする `runtime_exception` オブジェクトです。

### <a name="return-value"></a>戻り値

この `runtime_exception` オブジェクトへの参照。

## <a name="see-also"></a>関連項目

[同時実行名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
