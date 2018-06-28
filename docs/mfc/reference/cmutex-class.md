---
title: CMutex クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
dev_langs:
- C++
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3bde85e64fe8593ec2637e767e8c3c70d3b8200
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038078"
---
# <a name="cmutex-class"></a>CMutex クラス
「ミュー テックス」を表す、リソースへの 1 つのスレッド相互に排他的アクセスを許可する同期オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMutex : public CSyncObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMutex::CMutex](#cmutex)|`CMutex` オブジェクトを構築します。|  
  
## <a name="remarks"></a>Remarks  
 ミュー テックスは、一度に 1 つのスレッドできるようにするデータまたはその他の制御されたリソースを変更する場合に便利です。 たとえば、リンク リスト ノードの追加は、一度に 1 つのスレッドでのみ許可するプロセスです。 使用して、`CMutex`だけで、一度に 1 つのスレッドが一覧にアクセスできるリンクの一覧を制御するオブジェクト。  
  
 使用する、`CMutex`オブジェクトを構築、`CMutex`オブジェクトが必要なとき。 、を待機するミュー テックスの名前を指定し、アプリケーションで最初に所有する必要があります。 コンス トラクターは、制御が戻るとき、ミュー テックスにアクセスできます。 呼び出す[したら](../../mfc/reference/csyncobject-class.md#unlock)が完了すると被制御リソースにアクセスします。  
  
 使用する代替方法`CMutex`オブジェクトは、型の変数を追加する`CMutex`を制御したいクラスのデータ メンバーとして。 コンス トラクターの呼び出し、制御されるオブジェクトの構築時に、`CMutex`データ メンバー、ミュー テックスが最初に所有されている、ミュー テックスの名前 (場合に、プロセス境界を越えて使用されます)、およびセキュリティ属性を必要なかどうかを指定します。  
  
 によって制御されるリソースにアクセスする`CMutex`オブジェクトがこの方法では、いずれかの型の変数をまず作成[CSingleLock](../../mfc/reference/csinglelock-class.md)または型[CMultiLock](../../mfc/reference/cmultilock-class.md)リソースのアクセス メンバー関数。 まず、ロック オブジェクトの`Lock`メンバー関数 (たとえば、 [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock))。 この時点では、スレッドはいずれか、リソースにアクセスをお待ちのリソースを解放して、アクセスを取得またはリソースが解放されるまで、リソースにアクセスするために失敗して、タイムアウトまで待機します。 いずれの場合、リソースがスレッド セーフな方法でアクセスされました。 リソースを解放するには、ロック オブジェクトを使用して`Unlock`メンバー関数 (たとえば、 [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock))、ロック オブジェクトがスコープから除外できるようにするか。  
  
 使用する方法についての`CMutex`、オブジェクトが、記事を参照して[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxmt.h  
  
##  <a name="cmutex"></a>  CMutex::CMutex  
 名前付きまたは名前のない構築`CMutex`オブジェクト。  
  
```  
CMutex(
    BOOL bInitiallyOwn = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *bInitiallyOwn*  
 場合を指定のスレッドの作成、`CMutex`オブジェクトが最初に、ミュー テックスによって制御されているリソースへのアクセスを持ちます。  
  
 *lpszName*  
 `CMutex` オブジェクトの名前。 同じ名前の別のミュー テックスが存在する場合、 *lpszName*プロセス境界をまたいでオブジェクトを使用する場合に指定する必要があります。 場合**NULL**、ミュー テックスは名前付きできません。 コンス トラクターは、ビルド、新しい名前には、既存のミュー テックスが一致すると、`CMutex`その名前のミュー テックスを参照するオブジェクト。 名前には、ミュー テックスではない既存の同期オブジェクトが一致すると、構築が失敗します。  
  
 *lpsaAttribute*  
 ミュー テックス オブジェクトのセキュリティ属性。 この構造体の詳細を参照してください。 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK に含まれています。  
  
### <a name="remarks"></a>Remarks  
 アクセスまたはリリース、`CMutex`オブジェクトを作成、 [CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトと呼び出しの[ロック](../../mfc/reference/csinglelock-class.md#lock)と[Unlock](../../mfc/reference/csinglelock-class.md#unlock)メンバー関数。 場合、`CMutex`オブジェクトがスタンドアロンの使用にされている場合、呼び出し、`Unlock`メンバー関数をそれを解放します。  
  
> [!IMPORTANT]
>  作成した後、`CMutex`オブジェクトを使用して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)をミュー テックスが既に存在しないことを確認します。 ミュー テックスが予期せず存在、悪意のあるプロセスが発生したり、悪意ミュー テックスを使用することがある必ずしも意図している可能性があります。 ここでは、推奨されるセキュリティを考慮したプロシージャがハンドルを終了し、クリックすると、オブジェクトの作成でエラーが発生しました。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/csyncobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



