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
ms.openlocfilehash: 26e1fd55d321b221f4732874d57d02a79c4c6398
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318500"
---
# <a name="csemaphore-class"></a>CSemaphore クラス

クラス`CSemaphore`のオブジェクトは、"セマフォ" (1 つ以上のプロセス内の限られた数のスレッドが、指定されたリソースに現在アクセスしているスレッド数の数を管理する) にアクセスできるようにする同期オブジェクトを表します。

## <a name="syntax"></a>構文

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[セマフォ::セマフォ](#csemaphore)|`CSemaphore` オブジェクトを構築します。|

## <a name="remarks"></a>解説

セマフォは、限られた数のユーザーしかサポートできない共有リソースへのアクセスを制御する場合に役立ちます。 オブジェクトの現在の`CSemaphore`数は、追加可能なユーザーの数です。 カウントがゼロになると、`CSemaphore`オブジェクトによって制御されるリソースを使用しようとする試みはすべてシステムキューに挿入され、タイムアウトになるか、カウントが 0 より大きくなるまで待機します。 オブジェクトの構築時に、制御されたリソースに一度にアクセスできるユーザーの最大数が`CSemaphore`指定されます。

オブジェクトを`CSemaphore`使用するには、必要なときに`CSemaphore`オブジェクトを構築します。 待機するセマフォの名前を指定し、アプリケーションが最初に所有するようにします。 コンストラクターが戻ったときに、セマフォにアクセスできます。 制御されたリソースへのアクセスが完了したら[、CSyncObject::ロック解除](../../mfc/reference/csyncobject-class.md#unlock)を呼び出します。

オブジェクトを使用`CSemaphore`する別の方法として、制御するクラスに`CSemaphore`データ メンバーとして型の変数を追加します。 制御されたオブジェクトの構築時に、初期アクセス数、`CSemaphore`最大アクセス数、セマフォの名前 (プロセス境界を越えて使用される場合)、および必要なセキュリティ属性を指定するデータ メンバーのコンストラクターを呼び出します。

この方法でオブジェクトによって`CSemaphore`制御されるリソースにアクセスするには、まず、CSingleLock[CSingleLock](../../mfc/reference/csinglelock-class.md)型の変数を作成するか、リソースのアクセス メンバー関数に[CMultiLock](../../mfc/reference/cmultilock-class.md)型を入力します。 次に、ロック オブジェクトの`Lock`メンバー関数を呼び出します (たとえば[、CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock))。 この時点で、スレッドはリソースへのアクセス権を取得するか、リソースが解放されてアクセスできるようになるのを待つか、リソースが解放されてタイムアウトするまで待機してリソースにアクセスできないかのどちらかです。 いずれの場合も、リソースはスレッド セーフな方法でアクセスされています。 リソースを解放するには、ロック オブジェクトの`Unlock`メンバー関数 ([たとえば、CSingleLock::Unlock)](../../mfc/reference/csinglelock-class.md#unlock)を使用するか、ロック オブジェクトがスコープ外に収まるようにします。

または、オブジェクトをスタンドアロンで`CSemaphore`作成し、制御されたリソースにアクセスする前に明示的にアクセスすることもできます。 この方法は、ソース コードを読んでいる人に対して明確に行われますが、エラーが発生しやすくなります。

オブジェクトの使用方法`CSemaphore`の詳細については、「[マルチスレッド : 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmt.h

## <a name="csemaphorecsemaphore"></a><a name="csemaphore"></a>セマフォ::セマフォ

名前付きオブジェクトまたは名前`CSemaphore`のないオブジェクトを構築します。

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>パラメーター

*初期カウント*<br/>
セマフォの初期使用回数。 0 以上 *、lMaxCount*以下にする必要があります。

*カウントカウント*<br/>
セマフォの最大使用回数。 1 以上であることが必要です。

*名前*<br/>
セマフォの名前。 セマフォがプロセス境界を越えてアクセスされる場合は、指定する必要があります。 の`NULL`場合、オブジェクトは名前なしになります。 名前が既存のセマフォと一致する場合、コンストラクターは、その`CSemaphore`名前のセマフォを参照する新しいオブジェクトを構築します。 名前がセマフォではない既存の同期オブジェクトと一致する場合、構築は失敗します。

*lpsa 属性*<br/>
セマフォ オブジェクトのセキュリティ属性。 この構造の詳細については、Windows SDK の[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))を参照してください。

### <a name="remarks"></a>解説

`CSemaphore`オブジェクトにアクセスまたは解放するには[、CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトを作成し、[そのロック](../../mfc/reference/csinglelock-class.md#lock)と[ロック解除](../../mfc/reference/csinglelock-class.md#unlock)のメンバー関数を呼び出します。

> [!IMPORTANT]
> オブジェクトを作成`CSemaphore`した後[、GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を使用して、ミューテックスが存在していないことを確認します。 ミューテックスが予期せず存在した場合、不正なプロセスがスクワッティングしていることを示している可能性があり、悪意を持ってミューテックスを使用しようとしている可能性があります。 この場合、推奨されるセキュリティ上の問題を意識した手順は、ハンドルを閉じて、オブジェクトの作成に失敗したかのように続行することです。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/csyncobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
