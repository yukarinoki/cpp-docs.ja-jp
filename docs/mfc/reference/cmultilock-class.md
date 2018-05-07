---
title: CMultiLock クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CMultiLock [MFC], CMultiLock
- CMultiLock [MFC], IsLocked
- CMultiLock [MFC], Lock
- CMultiLock [MFC], Unlock
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5c5424018c3863ce64435bcc09d2d539560285e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmultilock-class"></a>CMultiLock クラス
マルチスレッド プログラムで複数のリソースのアクセス制御に使うアクセス コントロール機構を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMultiLock  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMultiLock::CMultiLock](#cmultilock)|`CMultiLock` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMultiLock::IsLocked](#islocked)|配列内の特定の同期オブジェクトがロックされているかどうかを判断します。|  
|[CMultiLock::Lock](#lock)|同期オブジェクトの配列を待機します。|  
|[CMultiLock::Unlock](#unlock)|すべての所有する同期オブジェクトを解放します。|  
  
## <a name="remarks"></a>コメント  
 `CMultiLock` 基本クラスはありません。  
  
 同期クラスを使用する[CSemaphore](../../mfc/reference/csemaphore-class.md)、 [CMutex](../../mfc/reference/cmutex-class.md)、および[CEvent](../../mfc/reference/cevent-class.md)、いずれかを作成することができます、 **CMultiLock**または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトを待機し、同期オブジェクトを解放します。 使用して**CMultiLock**特定の時点で使用できる複数のオブジェクトがある場合。 使用して`CSingleLock`のみ必要がある場合、一度に 1 つのオブジェクトで待機します。  
  
 使用する、 **CMultiLock**オブジェクト、最初待機する同期オブジェクトの配列を作成します。 次に、呼び出し、 **CMultiLock**被制御リソースのクラスのメンバー関数内のオブジェクトのコンス トラクターです。 まず、[ロック](#lock)リソースが利用可能なかどうかを判断するメンバー関数 (通知)。 いずれかの場合は、メンバー関数の残りの部分を続行します。 リソースが使用できない場合は、リソースが解放されるまでの時間数を指定した待つか、failure を返します。 リソースの使用が完了したらを呼び出して、 [Unlock](#unlock)関数の場合、 **CMultiLock**オブジェクトがもう一度、使用するか、許可、 **CMultiLock**オブジェクトを破棄します。  
  
 **CMultiLock**オブジェクトは、スレッドの数が多い場合、最も役に立つ`CEvent`オブジェクトに対応できます。 すべてを含む配列を作成、`CEvent`ポインター、および呼び出し`Lock`です。 これにより、イベントのいずれかが通知されるまで待機するスレッド。  
  
 使用する方法の詳細についての**CMultiLock** 、オブジェクトが、記事を参照して[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CMultiLock`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmt.h  
  
##  <a name="cmultilock"></a>  CMultiLock::CMultiLock  
 構築、 **CMultiLock**オブジェクト。  
  
```  
CMultiLock(
    CSyncObject* ppObjects [ ],  
    DWORD dwCount,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppObjects`  
 待機する同期オブジェクトへのポインターの配列。 ことはできません**NULL**です。  
  
 `dwCount`  
 内のオブジェクト数`ppObjects`です。 1 以上であることが必要です。  
  
 `bInitialLock`  
 最初に指定されたオブジェクトのいずれかにアクセスしようとするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 この関数は、待機する同期オブジェクトの配列の作成後に呼び出されます。 通常使用可能になる同期オブジェクトの 1 つを待機する必要があります、スレッド内から呼び出されます。  
  
##  <a name="islocked"></a>  CMultiLock::IsLocked  
 指定したオブジェクトが非シグナル状態かどうかを (使用不可)。  
  
```  
BOOL IsLocked(DWORD dwItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwItem*  
 状態が照会されるオブジェクトに対応するオブジェクトの配列内のインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したオブジェクトがロックされている場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="lock"></a>  CMultiLock::Lock  
 この関数に指定された同期オブジェクトによって制御されるリソースの 1 つ以上にアクセスするために、 **CMultiLock**コンス トラクターです。  
  
```  
DWORD Lock(
    DWORD dwTimeOut = INFINITE,  
    BOOL bWaitForAll = TRUE,  
    DWORD dwWakeMask = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTimeOut*  
 同期オブジェクトを使用できるまで待機する時間を指定します (通知)。 場合**無限**、`Lock`がオブジェクトを返す前に通知されるまで待機します。  
  
 `bWaitForAll`  
 返す前に、同時に待機しているすべてのオブジェクトをシグナル状態になる必要があるかどうかを指定します。 場合**FALSE**、`Lock`が待機しているオブジェクトのいずれかが通知されるときに返されます。  
  
 `dwWakeMask`  
 待機を中止できるはその他の条件を指定します。 このパラメーターの使用可能なオプションの一覧については、次を参照してください。 [MsgWaitForMultipleObjects](http://msdn.microsoft.com/library/windows/desktop/ms684242) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 場合`Lock`失敗すると、以下の値を返します - 1。 成功した場合、次の値のいずれかを返します。  
  
-   間**WAIT_OBJECT_0**と**WAIT_OBJECT_0** + (1 - オブジェクトの数)  
  
     場合`bWaitForAll`は**TRUE**、すべてのオブジェクトが (使用可能) に通知されます。 場合`bWaitForAll`は**FALSE**、戻り値の**WAIT_OBJECT_0**が通知されるオブジェクトのオブジェクトの配列内のインデックスが (使用可能)。  
  
- **WAIT_OBJECT_0** + (オブジェクトの数)  
  
     指定されたイベント`dwWakeMask`は、スレッドの入力キューで使用できます。  
  
-   間**WAIT_ABANDONED_0**と**WAIT_ABANDONED_0** + (1 - オブジェクトの数)  
  
     場合`bWaitForAll`は**TRUE**、すべてのオブジェクトがシグナル状態、および放棄されたミュー テックス オブジェクトは、少なくとも 1 つのオブジェクト。 場合`bWaitForAll`は**FALSE**、戻り値の**WAIT_ABANDONED_0**待機を実行する放棄されたミュー テックス オブジェクトのオブジェクトの配列内のインデックスです。  
  
- **正常に終了しました。**  
  
     指定したタイムアウト間隔*dwTimeOut*待機成功しません有効期限が切れています。  
  
### <a name="remarks"></a>コメント  
 場合`bWaitForAll`は**TRUE**、`Lock`は同時にすべての同期オブジェクトがシグナル状態になるとすぐに正常に復帰します。 場合`bWaitForAll`は**FALSE**、`Lock`が、1 つまたは複数の同期オブジェクトがシグナル状態にすぐに返されます。  
  
 場合`Lock`を待機するミリ秒単位で指定された数を超えないことが、すぐに返すことはありません、 *dwTimeOut*パラメーターを返す前にします。 場合*dwTimeOut*は**無限**、`Lock`オブジェクトへのアクセスが得られるか、条件で指定されるまでは返されません`dwWakeMask`が満たされています。 それ以外の場合`Lock`された同期オブジェクトを取得できない、これは正常に復帰以外の場合は、エラーが返されます。  
  
##  <a name="unlock"></a>  CMultiLock::Unlock  
 所有する同期オブジェクトを解放`CMultiLock`です。  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lCount`  
 解放する参照の数をカウントします。 1 以上であることが必要です。 場合は、指定された時間を最大値を超えるオブジェクトの数となる、カウントが変更されていないと、関数を返します**FALSE**です。  
  
 `lPrevCount`  
 同期オブジェクトが、前のカウントを受け取るように、変数へのポインター。 場合**NULL**、前のカウントは返されません。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は`CMultiLock`のデストラクターです。  
  
 最初のフォーム`Unlock`によって管理される同期オブジェクトのロックを解除しようとしています。`CMultiLock`です。 2 番目の形式の`Unlock`のロックを解除しようとする、`CSemaphore`が所有するオブジェクト`CMultiLock`です。 場合`CMultiLock`いずれかを所有していないロック`CSemaphore`オブジェクトを関数が返されます**FALSE**以外の場合が返されます**TRUE**です。 `lCount` および`lpPrevCount`のパラメーターと同じでは、まったく[CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)です。 2 番目の形式の`Unlock`は多重状況に該当することはほとんどありません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)



