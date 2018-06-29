---
title: CSingleLock クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 65e969607e4017191539a0b0301b0c27ccb9f1ae
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078985"
---
# <a name="csinglelock-class"></a>CSingleLock クラス
マルチスレッド プログラムで 1 つのリソースのアクセス制御に使うアクセス コントロール機構を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSingleLock  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSingleLock::CSingleLock](#csinglelock)|`CSingleLock` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSingleLock::IsLocked](#islocked)|オブジェクトがロックされているかどうかを判断します。|  
|[CSingleLock::Lock](#lock)|同期オブジェクトで待機します。|  
|[CSingleLock::Unlock](#unlock)|同期オブジェクトを解放します。|  
  
## <a name="remarks"></a>Remarks  
 `CSingleLock` 基本クラスはありません。  
  
 同期クラスを使用するために[CSemaphore](../../mfc/reference/csemaphore-class.md)、 [CMutex](../../mfc/reference/cmutex-class.md)、 [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)、および[CEvent](../../mfc/reference/cevent-class.md)、いずれかを作成する必要があります、`CSingleLock`または[CMultiLock](../../mfc/reference/cmultilock-class.md)オブジェクトを待機し、同期オブジェクトを解放します。 使用して`CSingleLock`のみ必要がある場合、一度に 1 つのオブジェクトで待機します。 使用して`CMultiLock`特定の時点で使用できる複数のオブジェクトがある場合。  
  
 使用する、`CSingleLock`オブジェクト、被制御リソースのクラスのメンバー関数内のコンス トラクターを呼び出します。 まず、 [IsLocked](#islocked)メンバー関数をリソースが利用可能なかどうかを判断します。 である場合は、メンバー関数の残りの部分を続行します。 リソースが使用できない場合は、リソースを解放する、指定された時間を待つか、エラーを返します。 リソースの使用が完了したらを呼び出して、 [Unlock](#unlock)関数の場合、`CSingleLock`オブジェクトがもう一度、使用するか、許可、`CSingleLock`オブジェクトを破棄します。  
  
 `CSingleLock` オブジェクトから派生したオブジェクトの存在を必要と[関数](../../mfc/reference/csyncobject-class.md)です。 これは、通常、被制御リソースのクラスのデータ メンバーです。 使用する方法の詳細についての`CSingleLock`、オブジェクトが、記事を参照して[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CSingleLock`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxmt.h  
  
##  <a name="csinglelock"></a>  CSingleLock::CSingleLock  
 `CSingleLock` オブジェクトを構築します。  
  
```  
explicit CSingleLock(
    CSyncObject* pObject,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pObject*  
 アクセスする同期オブジェクトを指します。 ことはできません**NULL**です。  
  
 *bInitialLock*  
 最初に指定されたオブジェクトにアクセスしようとするかどうかを指定します。  
  
### <a name="remarks"></a>Remarks  
 この関数は、被制御リソースのアクセス メンバー関数内から通常呼び出されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]  
  
##  <a name="islocked"></a>  CSingleLock::IsLocked  
 オブジェクトに関連付けられているかどうかを判断、`CSingleLock`オブジェクトが非シグナル状態 (利用不可)。  
  
```  
BOOL IsLocked();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトがロックされている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]  
  
##  <a name="lock"></a>  CSingleLock::Lock  
 この関数に指定された同期オブジェクトによって制御されているリソースにアクセスするために、`CSingleLock`コンス トラクターです。  
  
```  
BOOL Lock(DWORD dwTimeOut = INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTimeOut*  
 同期オブジェクトを使用できるまで待機する時間を指定します (通知)。 場合**無限**、`Lock`がオブジェクトを返す前に通知されるまで待機します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 同期オブジェクトがシグナル状態される場合`Lock`は正常に復帰して、スレッドは、オブジェクトを所有します。 同期オブジェクトが非シグナル状態の場合 (利用不可)、`Lock`同期オブジェクトで指定されたミリ秒数までシグナル状態になるを待機は、 *dwTimeOut*パラメーター。 同期オブジェクトが指定された時間内シグナル状態になるいないしなかった場合`Lock`エラーを返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
##  <a name="unlock"></a>  CSingleLock::Unlock  
 所有する同期オブジェクトを解放`CSingleLock`です。  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lCount*  
 リリースへのアクセス数。 1 以上であることが必要です。 場合は、指定された時間を最大値を超えるオブジェクトの数となる、カウントが変更されていないと、関数を返します**FALSE**です。  
  
 *lPrevCount*  
 同期オブジェクトの前のカウントを受け取るように、変数へのポインター。 場合**NULL**、前のカウントは返されません。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数は`CSingleLock`のデストラクターです。  
  
 複数のアクセス数、セマフォを解放する必要がある場合は、2 番目の形式を使用して`Unlock`リリースへのアクセスの数を指定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMultiLock クラス](../../mfc/reference/cmultilock-class.md)
