---
title: CAutoPtr クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoPtr
- ATLBASE/ATL::CAutoPtr
- ATLBASE/ATL::CAutoPtr::CAutoPtr
- ATLBASE/ATL::CAutoPtr::Attach
- ATLBASE/ATL::CAutoPtr::Detach
- ATLBASE/ATL::CAutoPtr::Free
- ATLBASE/ATL::CAutoPtr::m_p
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edf1baff50541dd5f16c27205f300558558d6f92
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363201"
---
# <a name="cautoptr-class"></a>CAutoPtr クラス
このクラスは、スマート ポインター オブジェクトを表します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>  
class CAutoPtr
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ポインター型です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoPtr::CAutoPtr](#cautoptr)|コンストラクターです。|  
|[CAutoPtr:: ~ CAutoPtr](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoPtr::Attach](#attach)|このメソッドを呼び出して既存のポインターの所有権を取得します。|  
|[CAutoPtr::Detach](#detach)|ポインターの所有権を解放するには、このメソッドを呼び出します。|  
|[CAutoPtr::Free](#free)|指すオブジェクトを削除するには、このメソッドを呼び出して、`CAutoPtr`です。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoPtr::operator T *](#operator_t_star)|キャスト演算子です。|  
|[CAutoPtr::operator =](#operator_eq)|代入演算子です。|  
|[CAutoPtr::operator -> します。](#operator_ptr)|メンバーへのポインター演算子です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoPtr::m_p](#m_p)|ポインターのデータ メンバー変数です。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、作成と管理のスコープ外になるときに自動的にリソースを解放することによってメモリ リークを防ぐことが、スマート ポインターのメソッドを提供します。  
  
 さらに、`CAutoPtr`のコピー コンス トラクターと代入演算子所有権を譲渡、ポインターのポインターを変換先のポインターにコピーし、元のポインターを NULL に設定します。 そのため 2 つあることはできません`CAutoPtr`は同じポインターを格納する各オブジェクトし、同じポインターを削除すると、2 回の可能性を低減これです。  
  
 `CAutoPtr` また、ポインターのコレクションの作成を簡略化します。 コレクション クラスを派生して、デストラクターをオーバーライドではなくのコレクションを作成する単純な`CAutoPtr`オブジェクト。 コレクションが削除されると、`CAutoPtr`オブジェクトがスコープ外に出るし、自動的に削除されます。  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)バリアントと同じ方法で動作`CAutoPtr`それらの割り当てし、C++ ではなく、異なるヒープ関数を使用しているメモリを解放する点を除いて、**新しい**と**削除**演算子。 [出たリソース](../../atl/reference/cautovectorptr-class.md)に似ていますが`CAutoPtr`、唯一の違いを使用すること**new[] をベクトル**と**ベクター delete[]** 空きメモリの割り当てとにします。  
  
 関連項目[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)と[CAutoPtrList](../../atl/reference/cautoptrlist-class.md)配列や、スマート ポインターのリストが必要な場合です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]  
  
##  <a name="attach"></a>  CAutoPtr::Attach  
 このメソッドを呼び出して既存のポインターの所有権を取得します。  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 `CAutoPtr` This ポインターの所有権を持つオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ときに、`CAutoPtr`オブジェクト ポインターの所有権は自動的に削除ポインターと、割り当てられているデータ スコープ外になったときにします。 場合[CAutoPtr::Detach](#detach)が呼び出されると、プログラマ再度責任を解放するいずれかの指定されたリソースが割り当てられます。  
  
 デバッグ ビルドで、アサーション場合にエラーが発生、 [CAutoPtr::m_p](#m_p)データ メンバーは、現在、既存の値を指します。 つまり、null はありません。  
  
### <a name="example"></a>例  
 例を参照してください、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)です。  
  
##  <a name="cautoptr"></a>  CAutoPtr::CAutoPtr  
 コンストラクターです。  
  
```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<> 
CAutoPtr(CAutoPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 既存のポインター。  
  
 `TSrc`  
 別に管理されている型`CAutoPtr`, 現在のオブジェクトを初期化するために使用されます。  
  
### <a name="remarks"></a>コメント  
 `CAutoPtr`既存のポインターを使用してオブジェクトを作成する、この場合、ポインターの所有権を転送します。  
  
### <a name="example"></a>例  
 例を参照してください、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)です。  
  
##  <a name="dtor"></a>  CAutoPtr:: ~ CAutoPtr  
 デストラクターです。  
  
```
~CAutoPtr() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたリソースを解放します。 呼び出し[CAutoPtr::Free](#free)です。  
  
##  <a name="detach"></a>  CAutoPtr::Detach  
 ポインターの所有権を解放するには、このメソッドを呼び出します。  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターのコピーを返します。  
  
### <a name="remarks"></a>コメント  
 ポインターの所有権を解放、 [CAutoPtr::m_p](#m_p)データ メンバー変数に NULL ポインターのコピーを返します。 呼び出した後**デタッチ**はプログラマを解放するまで割り当てられているリソースを`CAutoPtr`オブジェクト可能性がありますが以前と見なされます reponsibility です。  
  
### <a name="example"></a>例  
 例を参照してください、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)です。  
  
##  <a name="free"></a>  CAutoPtr::Free  
 指すオブジェクトを削除するには、このメソッドを呼び出して、`CAutoPtr`です。  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>コメント  
 によって指されるオブジェクト、`CAutoPtr`が解放されると、 [CAutoPtr::m_p](#m_p)データ メンバー変数が NULL に設定します。  
  
##  <a name="m_p"></a>  CAutoPtr::m_p  
 ポインターのデータ メンバー変数です。  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー変数は、ポインターの情報を保持します。  
  
##  <a name="operator_eq"></a>  CAutoPtr::operator =  
 代入演算子です。  
  
```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 ポインター。  
  
 `TSrc`  
 クラスの型。  
  
### <a name="return-value"></a>戻り値  
 参照を返します、 **CAutoPtr\< T >** です。  
  
### <a name="remarks"></a>コメント  
 代入演算子の関連付けを解除、`CAutoPtr`オブジェクトを現在のポインターから、新しいポインターのアタッチと`p`代わりにします。  
  
### <a name="example"></a>例  
 例を参照してください、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)です。  
  
##  <a name="operator_ptr"></a>  CAutoPtr::operator-&gt;  
 メンバーへのポインター演算子です。  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 値を返します、 [CAutoPtr::m_p](#m_p)データ メンバー変数。  
  
### <a name="remarks"></a>コメント  
 この演算子によって示されるクラスのメソッドを呼び出すを使用して、`CAutoPtr`オブジェクト。 デバッグ ビルドで、アサーション場合にエラーが発生、 `CAutoPtr` NULL を指します。  
  
### <a name="example"></a>例  
 例を参照してください、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)です。  
  
##  <a name="operator_t_star"></a>  CAutoPtr::operator T *  
 キャスト演算子です。  
  
```  
operator T* () const throw();
```  
  
### <a name="return-value"></a>戻り値  
 クラス テンプレートで定義されたオブジェクト データ型へのポインターを返します。  
  
### <a name="example"></a>例  
 例を参照してください、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [出たリソース クラス](../../atl/reference/cautovectorptr-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
