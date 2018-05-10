---
title: CComCriticalSection クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
dev_langs:
- C++
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25376aba3cfbade202d1cf95c2218e88713ac22a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="ccomcriticalsection-class"></a>CComCriticalSection クラス
このクラスは、取得し、クリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComCriticalSection
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComCriticalSection::Init](#init)|作成し、クリティカル セクション オブジェクトを初期化します。|  
|[CComCriticalSection::Lock](#lock)|クリティカル セクション オブジェクトの所有権を取得します。|  
|[CComCriticalSection::Term](#term)|クリティカル セクション オブジェクトによって使用されるシステム リソースを解放します。|  
|[CComCriticalSection::Unlock](#unlock)|クリティカル セクション オブジェクトの所有権を解放します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComCriticalSection::m_sec](#m_sec)|A **CRITICAL_SECTION**オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CComCriticalSection` クラスに似ています[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)ただし、するには、明示的に初期化して、リリースの重要なセクションです。  
  
 通常、使用して`CComCriticalSection`を通じて、`typedef`名前[CriticalSection](ccommultithreadmodel-class.md#criticalsection)です。 この名前を参照して`CComCriticalSection`とき[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)が使用されています。  

  
 参照してください[CComCritSecLock クラス](../../atl/reference/ccomcritseclock-class.md)呼び出しよりも、このクラスを使用するより安全な方法を`Lock`と`Unlock`直接です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="ccomcriticalsection"></a>  CComCriticalSection::CComCriticalSection  
 コンストラクターです。  
  
```
CComCriticalSection() throw();
```  
  
### <a name="remarks"></a>コメント  
 セット、 [m_sec](#m_sec)データ メンバーを NULL に**です。**  
  
##  <a name="init"></a>  CComCriticalSection::Init  
 Win32 関数を呼び出す[InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472)に含まれているクリティカル セクション オブジェクトを初期化しますが、 [m_sec](#m_sec)データ メンバーです。  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、 **E_OUTOFMEMORY**または**E_FAIL**エラー発生時にします。  
  
##  <a name="lock"></a>  CComCriticalSection::Lock  
 Win32 関数を呼び出す[EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608)、スレッドに含まれているクリティカル セクション オブジェクトの所有権を取得できるまで待機したどの、 [m_sec](#m_sec)データ メンバーです。  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、 **E_OUTOFMEMORY**または**E_FAIL**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 呼び出して、クリティカル セクション オブジェクトを初期化最初必要があります、 [Init](#init)メソッドです。 保護されているコードの実行が完了すると、スレッドで呼び出す必要があります[Unlock](#unlock)クリティカル セクションの所有権を解放します。  
  
##  <a name="m_sec"></a>  CComCriticalSection::m_sec  
 クリティカル セクション オブジェクトすべてで使用を含む`CComCriticalSection`メソッドです。  
  
```
CRITICAL_SECTION m_sec;
```  
  
##  <a name="term"></a>  CComCriticalSection::Term  
 Win32 関数を呼び出す[DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552)に含まれているクリティカル セクション オブジェクトによって使用されているすべてのリソースを解放する、 [m_sec](#m_sec)データ メンバーです。  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 1 回`Term`が呼び出されると、重要な項目の同期 セクションを使用できなくできます。  
  
##  <a name="unlock"></a>  CComCriticalSection::Unlock  
 Win32 関数を呼び出す[LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169)に含まれているクリティカル セクション オブジェクトの所有権を解放する、 [m_sec](#m_sec)データ メンバーです。  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 所有権を取得するスレッドを呼び出す必要があります、[ロック](#lock)メソッドです。 各呼び出し`Lock`に対応する呼び出しが必要です`Unlock`クリティカル セクションの所有権を解放します。  
  
## <a name="see-also"></a>関連項目  
 [CComFakeCriticalSection クラス](../../atl/reference/ccomfakecriticalsection-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComCritSecLock クラス](../../atl/reference/ccomcritseclock-class.md)
