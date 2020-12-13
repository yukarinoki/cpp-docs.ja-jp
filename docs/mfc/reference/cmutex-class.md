---
description: '詳細情報: CMutex クラス'
title: CMutex クラス
ms.date: 11/04/2016
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
ms.openlocfilehash: 4890a99d52fb8142bac0cc25d6a23ef6dbcaed5b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331490"
---
# <a name="cmutex-class"></a>CMutex クラス

"Mutex" を表します。これは、1つのスレッドがリソースに相互に排他的にアクセスできるようにする同期オブジェクトです。

## <a name="syntax"></a>構文

```
class CMutex : public CSyncObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMutex:: CMutex](#cmutex)|`CMutex` オブジェクトを構築します。|

## <a name="remarks"></a>解説

ミューテックスは、一度に1つのスレッドのみがデータまたはその他の制御されたリソースを変更できるようにする場合に便利です。 たとえば、リンクリストへのノードの追加は、一度に1つのスレッドによってのみ許可されるプロセスです。 オブジェクトを使用して `CMutex` リンクリストを制御することにより、一度に1つのスレッドだけがリストにアクセスできます。

オブジェクトを使用するには `CMutex` 、 `CMutex` 必要に応じてオブジェクトを構築します。 待機するミューテックスの名前を指定し、アプリケーションで最初に所有する必要があります。 その後、コンストラクターから制御が戻ったときに mutex にアクセスできます。 制御されたリソースへのアクセスが完了したら、 [CSyncObject:: Unlock](../../mfc/reference/csyncobject-class.md#unlock) を呼び出します。

オブジェクトを使用する別の方法として、 `CMutex` `CMutex` 制御するクラスにデータメンバーとして型の変数を追加する方法があります。 制御されたオブジェクトの構築時に、 `CMutex` ミューテックスが最初に所有されているかどうか、ミューテックスの名前 (プロセスの境界を越えて使用される場合)、および必要なセキュリティ属性を指定して、データメンバーのコンストラクターを呼び出します。

この方法でオブジェクトによって制御されるリソースにアクセスするに `CMutex` は、まず、 [CSingleLock](../../mfc/reference/csinglelock-class.md) 型の変数を作成するか、リソースのアクセスメンバー関数に [CMultiLock](../../mfc/reference/cmultilock-class.md) を入力します。 次に、lock オブジェクトの `Lock` メンバー関数 (たとえば、 [CSingleLock:: lock](../../mfc/reference/csinglelock-class.md#lock)) を呼び出します。 この時点で、スレッドはリソースへのアクセスを取得し、リソースが解放されてアクセスできるまで待機します。または、リソースが解放され、タイムアウトになるまで待機し、リソースへのアクセスを取得できなくなります。 いずれの場合も、スレッドセーフな方法でリソースにアクセスしています。 リソースを解放するには、lock オブジェクトの `Unlock` メンバー関数 (たとえば、 [CSingleLock:: Unlock](../../mfc/reference/csinglelock-class.md#unlock)) を使用するか、ロックオブジェクトがスコープ外に出ることを許可します。

オブジェクトの使用方法の詳細については、 `CMutex` 「 [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>要件

**ヘッダー:** afxmt

## <a name="cmutexcmutex"></a><a name="cmutex"></a> CMutex:: CMutex

名前付きオブジェクトまたは名前のないオブジェクトを構築 `CMutex` します。

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>パラメーター

*ビン分割*<br/>
オブジェクトを作成するスレッド `CMutex` が、最初にミューテックスによって制御されるリソースにアクセスできるかどうかを指定します。

*lpszName*<br/>
`CMutex` オブジェクトの名前。 同じ名前の別のミューテックスが存在する場合、オブジェクトがプロセスの境界を越えて使用される場合は、 *Lpszname* を指定する必要があります。 **NULL** の場合、ミューテックスは無名になります。 名前が既存のミューテックスと一致する場合、コンストラクターは `CMutex` その名前のミューテックスを参照する新しいオブジェクトを作成します。 名前がミューテックスではない既存の同期オブジェクトと一致する場合、構築は失敗します。

*lpsaAttribute*<br/>
Mutex オブジェクトのセキュリティ属性。 この構造の詳細については、Windows SDK の「 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 」を参照してください。

### <a name="remarks"></a>解説

オブジェクトにアクセスしたり解放したりするには `CMutex` 、 [CMultiLock](../../mfc/reference/cmultilock-class.md) オブジェクトまたは [CSingleLock](../../mfc/reference/csinglelock-class.md) オブジェクトを作成し、その [Lock](../../mfc/reference/csinglelock-class.md#lock) および [Unlock](../../mfc/reference/csinglelock-class.md#unlock) メンバー関数を呼び出します。 `CMutex`オブジェクトがスタンドアロンで使用されている場合は、その `Unlock` メンバー関数を呼び出して解放します。

> [!IMPORTANT]
> オブジェクトを作成した後 `CMutex` 、 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) を使用して、ミューテックスが既に存在していないことを確認します。 ミューテックスが予期せずに存在する場合は、不正なプロセスがスクワッティングであることを示している可能性があります。また、ミューテックスを悪用する可能性があります。 この場合、推奨されるセキュリティ意識の高い手順は、ハンドルを閉じて、オブジェクトの作成でエラーが発生したかのように続行することです。

## <a name="see-also"></a>関連項目

[CSyncObject クラス](../../mfc/reference/csyncobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
