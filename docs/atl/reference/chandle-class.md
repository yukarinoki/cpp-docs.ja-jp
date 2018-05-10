---
title: CHandle クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHandle
- ATLBASE/ATL::CHandle
- ATLBASE/ATL::CHandle::CHandle
- ATLBASE/ATL::CHandle::Attach
- ATLBASE/ATL::CHandle::Close
- ATLBASE/ATL::CHandle::Detach
- ATLBASE/ATL::CHandle::m_h
dev_langs:
- C++
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b57aab927380f8801c3b9cab258a695c7d8a59d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="chandle-class"></a>CHandle クラス
このクラスは、作成およびオブジェクトのハンドルを使用するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CHandle
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHandle::CHandle](#chandle)|コンストラクターです。|  
|[CHandle:: ~ CHandle](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHandle::Attach](#attach)|アタッチするには、このメソッドを呼び出して、`CHandle`オブジェクトを既存のハンドルにします。|  
|[CHandle::Close](#close)|終了するには、このメソッドを呼び出して、`CHandle`オブジェクト。|  
|[CHandle::Detach](#detach)|ハンドルをデタッチするには、このメソッドを呼び出して、`CHandle`オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CHandle::operator ハンドル](#operator_handle)|格納されたハンドルの値を返します。|  
|[CHandle::operator =](#operator_eq)|代入演算子。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CHandle::m_h](#m_h)|ハンドルを格納するメンバー変数です。|  
  
## <a name="remarks"></a>コメント  
 A `CHandle` 、ハンドルが必要なときに、オブジェクトを使用できます: がある主な相違点、`CHandle`オブジェクトが自動的に削除されます。  
  
> [!NOTE]
>  INVALID_HANDLE_VALUE を使用して他のユーザーに対し、いくつかの API 関数は、空または無効なハンドルとして NULL を使用します。 `CHandle` NULL では、のみの使用は、INVALID_HANDLE_VALUE を実際のハンドルとして扱われます。 INVALID_HANDLE_VALUE を返すことができる API を呼び出す場合は、呼び出す前にこの値をチェックする必要があります[CHandle::Attach](#attach)に渡すか、`CHandle`コンス トラクターを代わりに NULL を渡します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="attach"></a>  CHandle::Attach  
 アタッチするには、このメソッドを呼び出して、`CHandle`オブジェクトを既存のハンドルにします。  
  
```
void Attach(HANDLE h) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 `CHandle` ハンドルの所有権を`h`です。  
  
### <a name="remarks"></a>コメント  
 割り当てます、`CHandle`オブジェクトを`h`を処理します。 デバッグ ビルドは atlassert 場合`h`は NULL です。 ハンドルの妥当性に関するその他のチェックは行われません。  
  
##  <a name="chandle"></a>  CHandle::CHandle  
 コンストラクターです。  
  
```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 既存のハンドルまたは`CHandle`です。  
  
### <a name="remarks"></a>コメント  
 新たに作成`CHandle`オブジェクト、必要に応じて 既存のハンドルを使用してまたは`CHandle`オブジェクト。  
  
##  <a name="dtor"></a>  CHandle:: ~ CHandle  
 デストラクターです。  
  
```
~CHandle() throw();
```  
  
### <a name="remarks"></a>コメント  
 解放、`CHandle`呼び出して[CHandle::Close](#close)です。  
  
##  <a name="close"></a>  CHandle::Close  
 終了するには、このメソッドを呼び出して、`CHandle`オブジェクト。  
  
```
void Close() throw();
```  
  
### <a name="remarks"></a>コメント  
 開いているオブジェクト ハンドルを閉じます。 ハンドルが NULL の場合、大文字の場合となる**閉じる**は既に呼び出されると、ATLASSERT がデバッグ ビルドで発生します。  
  
##  <a name="detach"></a>  CHandle::Detach  
 ハンドルをデタッチするには、このメソッドを呼び出して、`CHandle`オブジェクト。  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされているハンドルを返します。  
  
### <a name="remarks"></a>コメント  
 ハンドルの所有権を解放します。  
  
##  <a name="m_h"></a>  CHandle::m_h  
 ハンドルを格納するメンバー変数です。  
  
```
HANDLE m_h;
```  
  
##  <a name="operator_eq"></a>  CHandle::operator =  
 代入演算子です。  
  
```
CHandle& operator=(CHandle& h) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `h`  
 `CHandle` ハンドルの所有権を`h`です。  
  
### <a name="return-value"></a>戻り値  
 新しいへの参照を返します`CHandle`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 場合、`CHandle`オブジェクトが現在のハンドルを含む、閉じられます。 `CHandle`オブジェクトに渡されるが、そのハンドルの参照を NULL に設定します。 これにより、2 つ`CHandle`オブジェクトは、同じアクティブなハンドルを含めることはありません。  
  
##  <a name="operator_handle"></a>  CHandle::operator ハンドル  
 格納されたハンドルの値を返します。  
  
```  
operator HANDLE() const throw();
```  
  
### <a name="remarks"></a>コメント  
 格納されている値を返します[CHandle::m_h](#m_h)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
