---
description: 詳細については、「CSemaphore クラス」を参照してください。
title: CSemaphore クラス
ms.date: 11/04/2016
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
ms.openlocfilehash: 102b7ac9d7f934e3a04783c9ab537a858541c780
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264701"
---
# <a name="csemaphore-class"></a>CSemaphore クラス

クラスのオブジェクトは、 `CSemaphore` "セマフォ" を表します。これは、1つ以上のプロセス内の限られた数のスレッドがにアクセスできるようにする同期オブジェクトです。これにより、指定したリソースに現在アクセスしているスレッド数のカウントが保持されます。

## <a name="syntax"></a>構文

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSemaphore:: CSemaphore](#csemaphore)|`CSemaphore` オブジェクトを構築します。|

## <a name="remarks"></a>解説

セマフォは、限られた数のユーザーのみをサポートする共有リソースへのアクセスを制御する場合に役立ちます。 オブジェクトの現在の数 `CSemaphore` は、許可されている追加ユーザーの数です。 カウントがゼロになると、そのオブジェクトによって制御されるリソースを使用しようとするすべての試行 `CSemaphore` がシステムキューに挿入され、タイムアウトになるか、カウントが0を超えるまで待機します。 コントロールされたリソースに一度にアクセスできるユーザーの最大数は、オブジェクトの構築時に指定し `CSemaphore` ます。

オブジェクトを使用するには `CSemaphore` 、 `CSemaphore` 必要に応じてオブジェクトを構築します。 待機するセマフォの名前を指定し、アプリケーションで最初に所有する必要があることを指定します。 コンストラクターが返されたときに、セマフォにアクセスできます。 制御されたリソースへのアクセスが完了したら、 [CSyncObject:: Unlock](../../mfc/reference/csyncobject-class.md#unlock) を呼び出します。

オブジェクトを使用する別の方法として、 `CSemaphore` `CSemaphore` 制御するクラスにデータメンバーとして型の変数を追加する方法があります。 制御されたオブジェクトの構築時に、 `CSemaphore` 初期アクセス数、最大アクセス数、セマフォの名前 (プロセスの境界を越えて使用される場合)、および必要なセキュリティ属性を指定して、データメンバーのコンストラクターを呼び出します。

この方法でオブジェクトによって制御されるリソースにアクセスするに `CSemaphore` は、まず、 [CSingleLock](../../mfc/reference/csinglelock-class.md) 型の変数を作成するか、リソースのアクセスメンバー関数に [CMultiLock](../../mfc/reference/cmultilock-class.md) を入力します。 次に、lock オブジェクトの `Lock` メンバー関数 (たとえば、 [CSingleLock:: lock](../../mfc/reference/csinglelock-class.md#lock)) を呼び出します。 この時点で、スレッドはリソースへのアクセスを取得し、リソースが解放されてアクセスできるまで待機します。または、リソースが解放され、タイムアウトになるまで待機し、リソースへのアクセスを取得できなくなります。 いずれの場合も、スレッドセーフな方法でリソースにアクセスしています。 リソースを解放するには、lock オブジェクトの `Unlock` メンバー関数 (たとえば、 [CSingleLock:: Unlock](../../mfc/reference/csinglelock-class.md#unlock)) を使用するか、ロックオブジェクトがスコープ外に出ることを許可します。

または、 `CSemaphore` オブジェクトをスタンドアロンで作成し、制御されたリソースにアクセスする前に明示的にアクセスすることもできます。 このメソッドは、ソースコードを読んでいるユーザーにとってわかりやすく、エラーが発生しやすくなります。

オブジェクトの使用方法の詳細については、 `CSemaphore` 「 [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>要件

**ヘッダー:** afxmt

## <a name="csemaphorecsemaphore"></a><a name="csemaphore"></a> CSemaphore:: CSemaphore

名前付きオブジェクトまたは名前のないオブジェクトを構築 `CSemaphore` します。

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>パラメーター

*lInitialCount*<br/>
セマフォの初期の使用カウント。 0以上、 *lMaxCount* 以下である必要があります。

*lMaxCount*<br/>
セマフォの最大使用回数。 1 以上であることが必要です。

*pstrName*<br/>
セマフォの名前。 セマフォがプロセスの境界を越えてアクセスされる場合は、を指定する必要があります。 の場合 `NULL` 、オブジェクトには名前が付いていません。 名前が既存のセマフォと一致する場合、コンストラクターは `CSemaphore` その名前のセマフォを参照する新しいオブジェクトを作成します。 名前がセマフォではない既存の同期オブジェクトと一致する場合、構築は失敗します。

*lpsaAttributes*<br/>
セマフォオブジェクトのセキュリティ属性。 この構造の詳細については、Windows SDK の「 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 」を参照してください。

### <a name="remarks"></a>解説

オブジェクトにアクセスしたり解放したりするには `CSemaphore` 、 [CMultiLock](../../mfc/reference/cmultilock-class.md) オブジェクトまたは [CSingleLock](../../mfc/reference/csinglelock-class.md) オブジェクトを作成し、その [Lock](../../mfc/reference/csinglelock-class.md#lock) および [Unlock](../../mfc/reference/csinglelock-class.md#unlock) メンバー関数を呼び出します。

> [!IMPORTANT]
> オブジェクトを作成した後 `CSemaphore` 、 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) を使用して、ミューテックスが既に存在していないことを確認します。 ミューテックスが予期せずに存在する場合は、不正なプロセスがスクワッティングであることを示している可能性があります。また、ミューテックスを悪用する可能性があります。 この場合、推奨されるセキュリティ意識の高い手順は、ハンドルを閉じて、オブジェクトの作成でエラーが発生したかのように続行することです。

## <a name="see-also"></a>関連項目

[CSyncObject クラス](../../mfc/reference/csyncobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
