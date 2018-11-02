---
title: _com_ptr_t::_com_ptr_t
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::_com_ptr_t
helpviewer_keywords:
- _com_ptr_t method [C++]
ms.assetid: 0c00620a-28d2-4f60-ae4a-1696be36137e
ms.openlocfilehash: 456311c5299eb4275bba411a77911f7a9c7fb8c9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470776"
---
# <a name="comptrtcomptrt"></a>_com_ptr_t::_com_ptr_t

**Microsoft 固有の仕様**

構築、 **_com_ptr_t**オブジェクト。

## <a name="syntax"></a>構文

```
// Default constructor.
// Constructs a NULL smart pointer.
_com_ptr_t() throw();

// Constructs a NULL smart pointer. The NULL argument must be zero.
_com_ptr_t( 
   int null 
);

// Constructs a smart pointer as a copy of another instance of the
// same smart pointer. AddRef is called to increment the reference
// count for the encapsulated interface pointer.
_com_ptr_t( 
   const _com_ptr_t& cp 
) throw();

// Move constructor (Visual Studio 2015 Update 3 and later)
_com_ptr_t(_com_ptr_t&& cp) throw();

// Constructs a smart pointer from a raw interface pointer of this
// smart pointer's type. If fAddRef is true, AddRef is called
// to increment the reference count for the encapsulated
// interface pointer. If fAddRef is false, this constructor
// takes ownership of the raw interface pointer without calling AddRef.
_com_ptr_t( 
   Interface* pInterface, 
   bool fAddRef 
) throw();

// Construct pointer for a _variant_t object.
// Constructs a smart pointer from a _variant_t object. The
// encapsulated VARIANT must be of type VT_DISPATCH or VT_UNKNOWN, or
// it can be converted into one of these two types. If QueryInterface
// fails with an E_NOINTERFACE error, a NULL smart pointer is
// constructed.
_com_ptr_t( 
   const _variant_t& varSrc 
);

// Constructs a smart pointer given the CLSID of a coclass. This
// function calls CoCreateInstance, by the member function
//  CreateInstance, to create a new COM object and then queries for
// this smart pointer's interface type. If QueryInterface fails with
// an E_NOINTERFACE error, a NULL smart pointer is constructed.
explicit _com_ptr_t( 
   const CLSID& clsid,  
   IUnknown* pOuter = NULL,  
   DWORD dwClsContext = CLSCTX_ALL 
);

// Calls CoCreateClass with provided CLSID retrieved from string.
explicit _com_ptr_t( 
   LPCWSTR str,  
   IUnknown* pOuter = NULL,  
   DWORD dwClsContext = CLSCTX_ALL 
);

// Constructs a smart pointer given a multibyte character string that
// holds either a CLSID (starting with "{") or a ProgID. This function
// calls CoCreateInstance, by the member function CreateInstance, to
// create a new COM object and then queries for this smart pointer's
// interface type. If QueryInterface fails with an E_NOINTERFACE error,
// a NULL smart pointer is constructed.
explicit _com_ptr_t( 
   LPCSTR str, 
   IUnknown* pOuter = NULL, 
   DWORD dwClsContext = CLSCTX_ALL 
);

// Saves the interface.
template<>  
_com_ptr_t( 
   Interface* pInterface 
) throw();

// Make sure correct ctor is called
template<>  
_com_ptr_t( 
   LPSTR str 
);

// Make sure correct ctor is called
template<>  
_com_ptr_t( 
   LPWSTR str 
);

// Constructs a smart pointer from a different smart pointer type or
// from a different raw interface pointer. QueryInterface is called to
// find an interface pointer of this smart pointer's type. If
// QueryInterface fails with an E_NOINTERFACE error, a NULL smart
// pointer is constructed.
template<typename _OtherIID>  
_com_ptr_t( 
   const _com_ptr_t<_OtherIID>& p 
);

// Constructs a smart-pointer from any IUnknown-based interface pointer.
template<typename _InterfaceType> 
_com_ptr_t( 
   _InterfaceType* p 
);

// Disable conversion using _com_ptr_t* specialization of
// template<typename _InterfaceType> _com_ptr_t(_InterfaceType* p)
template<>  
explicit _com_ptr_t( 
   _com_ptr_t* p 
);
```

#### <a name="parameters"></a>パラメーター

*pInterface*<br/>
生のインターフェイス ポインター。

*fAddRef*<br/>
TRUE の場合、`AddRef`カプセル化されたインターフェイス ポインターの参照カウントをインクリメントすると呼びます。

*cp*<br/>
A **_com_ptr_t**オブジェクト。

*p*<br/>
このスマート ポインター型と異なる型で生のインターフェイス ポインター **_com_ptr_t**オブジェクト。

*varSrc*<br/>
`_variant_t` オブジェクト。

*clsid*<br/>
`CLSID`コクラスの。

*dwClsContext*<br/>
実行可能コードを実行するコンテキスト。

*lpcStr*<br/>
保持するマルチバイト文字列を`CLSID`(以降では"**{**") または`ProgID`します。

*pOuter*<br/>
不明な外部の[集計](/windows/desktop/com/aggregation)します。

## <a name="see-also"></a>関連項目

[_com_ptr_t クラス](../cpp/com-ptr-t-class.md)