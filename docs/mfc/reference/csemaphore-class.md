---
title: CSemaphore クラス
ms.date: 11/04/2016
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
ms.openlocfilehash: f2a05963f39393bcc73650beb44c5dbb8e5535ee
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274220"
---
# <a name="csemaphore-class"></a>CSemaphore クラス

クラスのオブジェクト`CSemaphore`「セマフォ」を表します: 現在、指定したリソースにアクセスするスレッドの数にアクセスを管理する 1 つまたは複数のプロセスでのスレッドの数に制限ができるようにする同期オブジェクト。

## <a name="syntax"></a>構文

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSemaphore::CSemaphore](#csemaphore)|`CSemaphore` オブジェクトを構築します。|

## <a name="remarks"></a>Remarks

セマフォは、ユーザーの数に制限をサポートできるだけ共有リソースへのアクセス制御に役立ちます。 現在のカウント、`CSemaphore`オブジェクトが許可されているその他のユーザーの数。 によって制御されるリソースを使用する試みがすべて、カウントがゼロに達すると、`CSemaphore`カウントが 0 またはオブジェクトがシステム キューに挿入され、タイムアウトされるまで待機します。 構築時に、制御されるリソースを同時にアクセスできるユーザーの最大数が指定されて、`CSemaphore`オブジェクト。

使用する、`CSemaphore`オブジェクト、構築、`CSemaphore`必要がある場合のオブジェクトします。 待機、セマフォの名前を指定し、アプリケーションが最初に所有する必要があります。 コンス トラクターは、返されるときに、セマフォをアクセスできます。 呼び出す[したら](../../mfc/reference/csyncobject-class.md#unlock)が終わったら、被制御リソースにアクセスします。

代替の方法を使用して`CSemaphore`オブジェクトは、型の変数を追加する`CSemaphore`を制御するクラスにデータ メンバーとして。 コンス トラクターを呼び出し、制御されるオブジェクトの構築時に、`CSemaphore`初期を指定するデータ メンバーがアクセス数、アクセスの最大数、(プロセスの境界を越えて使用) 場合、セマフォの名前および必要なセキュリティの属性。

によって制御されるリソースにアクセスする`CSemaphore`オブジェクトが、この方法では、いずれかの型の変数をまず作成[CSingleLock](../../mfc/reference/csinglelock-class.md)または型[CMultiLock](../../mfc/reference/cmultilock-class.md)リソースのアクセス メンバー関数。 呼び出して、ロック オブジェクトの`Lock`メンバー関数 (たとえば、 [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock))。 この時点では、スレッドはいずれか、リソースにアクセスを待機してから、リソースを解放して、アクセスを取得またはリソースが解放されると、リソースへのアクセスに失敗したときのタイムアウトを待ちます。 いずれの場合も、リソースがスレッド セーフな方法でアクセスされました。 リソースを解放するロック オブジェクトを使用して、`Unlock`メンバー関数 (たとえば、 [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock))、またはロック オブジェクトがスコープから除外できるようにします。

また、作成することができます、 `CSemaphore` 、スタンドアロン オブジェクトし、制御されたリソースへのアクセスを試みる前に明示的にアクセスします。 だれかが、ソース コードを読むにはわかり、このメソッドは、エラーが発生しやすいです。

使用する方法の詳細についての`CSemaphore`オブジェクトは、記事をご覧ください。[マルチ スレッド。同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmt.h

##  <a name="csemaphore"></a>  CSemaphore::CSemaphore

名前付きセーブポイントまたは名前のない、コンストラクト`CSemaphore`オブジェクト。

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>パラメーター

*lInitialCount*<br/>
セマフォの使用状況の初期数。 0 以上にする必要がありますに等しいまたはそれよりも小さいと*lMaxCount*します。

*lMaxCount*<br/>
セマフォの最大使用率カウントします。 1 以上であることが必要です。

*pstrName*<br/>
セマフォの名前。 プロセスの境界を越えて、セマフォがアクセスされる場合を指定する必要があります。 場合`NULL`オブジェクトの名前付きが解除されます。 名前が既存のセマフォに一致する場合、コンス トラクターは新しい`CSemaphore`その名前のセマフォを参照するオブジェクト。 名前には、セマフォではない既存の同期オブジェクトが一致すると、構築は失敗します。

*lpsaAttributes*<br/>
セマフォ オブジェクトのセキュリティ属性。 この構造体の詳細については、次を参照してください。 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK に含まれています。

### <a name="remarks"></a>Remarks

アクセスまたはリリースを`CSemaphore`オブジェクトを作成、 [CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトと呼び出しの[ロック](../../mfc/reference/csinglelock-class.md#lock)と[Unlock](../../mfc/reference/csinglelock-class.md#unlock)メンバー関数。

> [!IMPORTANT]
>  作成した後、`CSemaphore`オブジェクトを使用して[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)ミュー テックスがまだ存在しないことを確認します。 予期せずにミュー テックスが存在して、不正なプロセスが発生したり、悪意のあるミュー テックスを使用するつもりが可能性があります。 ここでは、セキュリティ意識の推奨手順は、ハンドルを終了し、クリックすると、オブジェクトの作成でエラーが発生しました。

## <a name="see-also"></a>関連項目

[CSyncObject クラス](../../mfc/reference/csyncobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
