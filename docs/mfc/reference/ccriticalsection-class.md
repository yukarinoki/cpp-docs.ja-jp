---
title: CCriticalSection クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
dev_langs:
- C++
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6aba8c9ebe1eee6ca80d17fdff20c7d3dc30e2ae
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956864"
---
# <a name="ccriticalsection-class"></a>メンバー クラス
「クリティカル セクション」を表す — リソースまたはコード セクションへのアクセスを一度に 1 つのスレッドをできるようにする同期オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCriticalSection::CCriticalSection](#ccriticalsection)|`CCriticalSection` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCriticalSection::Lock](#lock)|アクセスするために使用して、`CCriticalSection`オブジェクト。|  
|[CCriticalSection::Unlock](#unlock)|`CCriticalSection` のオブジェクトを解放します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|内部へのポインターを取得**CRITICAL_SECTION**オブジェクト。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CCriticalSection::m_sect](#m_sect)|A **CRITICAL_SECTION**オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 重要なセクションは、一度に 1 つのスレッドできるようにするデータまたはその他の制御されたリソースを変更する場合に便利です。 たとえば、リンク リスト ノードの追加は、一度に 1 つのスレッドでのみ許可するプロセスです。 使用して、`CCriticalSection`だけで、一度に 1 つのスレッドが一覧にアクセスできるリンクの一覧を制御するオブジェクト。  
  
> [!NOTE]
>  機能、`CCriticalSection`クラスが実際の Win32 によって提供される**CRITICAL_SECTION**オブジェクト。  
  
 重要なセクションがミュー テックスの代わりに使用されます (を参照してください[CMutex](../../mfc/reference/cmutex-class.md)) と速度が、プロセス境界をまたいでリソースは使用されません。  
  
 2 つのメソッドを使用するため、`CCriticalSection`オブジェクト: スタンドアロンおよびクラスに埋め込まれています。  
  
-   スタンドアロンを使用するスタンドアロン メソッド`CCriticalSection`オブジェクトを構築、`CCriticalSection`オブジェクトが必要なとき。 呼び出してオブジェクトを明示的にコンス トラクターから正常に返された後にロック[ロック](#lock)です。 呼び出す[Unlock](#unlock)が完了すると重要なセクションへのアクセスします。 このメソッドは、ソース コードを読む人にはわかりはロックし、アクセスの前後には、クリティカル セクションをロック解除することが、エラーが発生しやすいです。  
  
     使用するよりも適していますメソッドは、 [CSingleLock](../../mfc/reference/csinglelock-class.md)クラスです。 さらに、`Lock`と`Unlock`例外が発生した場合、リソースのロックを解除について心配するメソッドがありません。  
  
-   メソッドを追加することで、複数のスレッドを持つクラスを共有することも埋め込まれている、 `CCriticalSection`-型データ メンバーがクラスと必要なときに、データ メンバーをロックします。  
  
 使用する方法についての`CCriticalSection`、オブジェクトが、記事を参照して[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxmt.h  
  
##  <a name="ccriticalsection"></a>  CCriticalSection::CCriticalSection  
 `CCriticalSection` オブジェクトを構築します。  
  
```  
CCriticalSection();
```  
  
### <a name="remarks"></a>Remarks  
 アクセスまたはリリース、`CCriticalSection`オブジェクトを作成、 [CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトと呼び出しの[ロック](../../mfc/reference/csinglelock-class.md#lock)と[Unlock](../../mfc/reference/csinglelock-class.md#unlock)メンバー関数。 場合、`CCriticalSection`オブジェクトがスタンドアロンの使用にされている場合、呼び出し、 [Unlock](#unlock)解放するメンバー関数。  
  
 コンス トラクターが必要なシステム メモリ、メモリ不足の例外の割り当てに失敗したかどうか (型の[CMemoryException](../../mfc/reference/cmemoryexception-class.md)) が自動的にスローされます。  
  
### <a name="example"></a>例  
  例を参照して[CCriticalSection::Lock](#lock)です。  
  
##  <a name="lock"></a>  CCriticalSection::Lock  
 クリティカル セクション オブジェクトにアクセスするには、このメンバー関数を呼び出します。  
  
```  
BOOL Lock();  
BOOL Lock(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTimeout*  
 `Lock` このパラメーター値を無視します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 `Lock` クリティカル セクション オブジェクトがシグナル状態になるまでは返されませんをブロッキング呼び出し (できるようになります)。  
  
 使用することができますがタイムアウトしました待機が必要な場合、 [CMutex](../../mfc/reference/cmutex-class.md)オブジェクトの代わりに、`CCriticalSection`オブジェクト。  
  
 場合`Lock`が必要なシステム メモリ、メモリ不足の例外の割り当てに失敗した (型の[CMemoryException](../../mfc/reference/cmemoryexception-class.md)) が自動的にスローされます。  
  
### <a name="example"></a>例  
 この例では、共有リソースへのアクセスを制御することで、入れ子になったクリティカル セクションの方法を示します (静的`_strShared`オブジェクト)、共有を使用して`CCriticalSection`オブジェクト。 `SomeMethod`関数では、安全な方法で共有リソースの更新を示します。  
  
 [!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]  
  
##  <a name="m_sect"></a>  CCriticalSection::m_sect  
 クリティカル セクション オブジェクトすべてで使用を含む`CCriticalSection`メソッドです。  
  
```  
CRITICAL_SECTION m_sect;  
```  
  
##  <a name="operator_critical_section_star"></a>  CCriticalSection::operator CRITICAL_SECTION *  
 取得、 **CRITICAL_SECTION**オブジェクト。  
  
```  
operator CRITICAL_SECTION*();
```   
  
### <a name="remarks"></a>Remarks  
 内部へのポインターを取得するには、この関数を呼び出す**CRITICAL_SECTION**オブジェクト。  
  
##  <a name="unlock"></a>  CCriticalSection::Unlock  
 リリース、`CCriticalSection`別のスレッドで使用するオブジェクト。  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、`CCriticalSection`オブジェクトが、スレッドが所有して、リリースが正常に実行。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>Remarks  
 場合、`CCriticalSection`が使用されているスタンドアロン、`Unlock`クリティカル セクションによって制御されるリソースの使用の完了後すぐに呼び出す必要があります。 場合、 [CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトが使用されている、`CCriticalSection::Unlock`ロックのオブジェクトによって呼び出される`Unlock`メンバー関数。  
  
### <a name="example"></a>例  
  例を参照して[CCriticalSection::Lock](#lock)です。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/csyncobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMutex クラス](../../mfc/reference/cmutex-class.md)
