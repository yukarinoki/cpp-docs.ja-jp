---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bcc5290b08b6a0b6159c1ba9b0b5b05d02a178ba
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122070"
---
# <a name="csyncobject-class"></a>関数クラス
Win32 の同期オブジェクトに共通の機能を提供する純粋仮想クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CSyncObject : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSyncObject::CSyncObject](#csyncobject)|`CSyncObject` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSyncObject::Lock](#lock)|同期オブジェクトへのアクセスを向上します。|  
|[したら](#unlock)|同期オブジェクトへのアクセスを向上します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CSyncObject::operator ハンドル](#operator_handle)|同期オブジェクトへのアクセスを提供します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CSyncObject::m_hObject](#m_hobject)|基になる同期オブジェクトへのハンドル。|  
  
## <a name="remarks"></a>Remarks  
 Microsoft Foundation Class ライブラリは、いくつかのクラスから派生した`CSyncObject`です。 これらは[CEvent](../../mfc/reference/cevent-class.md)、 [CMutex](../../mfc/reference/cmutex-class.md)、 [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)、および[CSemaphore](../../mfc/reference/csemaphore-class.md)です。  
  
 同期オブジェクトを使用する方法については、記事を参照してください。[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxmt.h  
  
##  <a name="csyncobject"></a>  CSyncObject::CSyncObject  
 指定された名前を使用して、同期オブジェクトを構築します。  
  
```  
explicit CSyncObject(LPCTSTR pstrName);  
virtual ~CSyncObject();
```  
  
### <a name="parameters"></a>パラメーター  
 *pstrName*  
 オブジェクトの名前。 NULL の場合、 *pstrName*は null になります。  
  
##  <a name="lock"></a>  CSyncObject::Lock  
 同期オブジェクトによって制御されているリソースにアクセスするには、この関数を呼び出します。  
  
```  
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTimeout*  
 同期オブジェクトを使用できるまで待機するミリ秒単位の時間を指定します (通知)。 場合、無限`Lock`がオブジェクトを返す前に通知されるまで待機します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 同期オブジェクトがシグナル状態される場合`Lock`は正常に復帰して、スレッドは、オブジェクトを所有します。 同期オブジェクトが非シグナル状態の場合 (利用不可)、`Lock`同期オブジェクトで指定されたミリ秒数までシグナル状態になるを待機は、 *dwTimeOut*パラメーター。 同期オブジェクトが指定された時間内シグナル状態になるいないしなかった場合`Lock`エラーを返します。  
  
##  <a name="m_hobject"></a>  CSyncObject::m_hObject  
 基になる同期オブジェクトへのハンドル。  
  
```  
HANDLE m_hObject;  
```  
  
##  <a name="operator_handle"></a>  CSyncObject::operator ハンドル  
 この演算子のハンドルの取得を使用して、`CSyncObject`オブジェクト。  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、同期オブジェクトへのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 Windows Api を直接呼び出すために、ハンドルを使用することができます。  
  
##  <a name="unlock"></a>  したら  
 宣言`Unlock`パラメーターなしでは、純粋仮想関数とから派生するすべてのクラスでオーバーライドされる必要があります`CSyncObject`です。  
  
```  
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,  
    LPLONG lpPrevCount = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lCount*  
 既定の実装では使用されません。  
  
 *lpPrevCount*  
 既定の実装では使用されません。  
  
### <a name="return-value"></a>戻り値  
 常に既定の実装では、TRUE を返します。  
  
### <a name="remarks"></a>Remarks  
 常に、2 つのパラメーター宣言の既定の実装では、TRUE を返します。 この関数は呼び出し元のスレッドが所有する同期オブジェクトへのアクセスを解放します。 2 番目の宣言は、被制御リソースの 1 つ以上のアクセスを許可するセマフォなどの同期オブジェクトに対して提供されます。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



