---
title: CMutex クラス
ms.date: 11/04/2016
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
ms.openlocfilehash: 2d6f637ab4828b3e70df205ebf359ae45a940d60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363279"
---
# <a name="cmutex-class"></a>CMutex クラス

"ミューテックス" — 1 つのスレッドがリソースに相互に排他的にアクセスできるようにする同期オブジェクトを表します。

## <a name="syntax"></a>構文

```
class CMutex : public CSyncObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cミューテックス::Cミューテックス](#cmutex)|`CMutex` オブジェクトを構築します。|

## <a name="remarks"></a>解説

ミューテックスは、一度に 1 つのスレッドだけがデータまたはその他の制御されたリソースを変更できる場合に便利です。 たとえば、リンク リストにノードを追加するプロセスは、一度に 1 つのスレッドだけが許可する必要があります。 オブジェクトを`CMutex`使用してリンク リストを制御すると、一度に 1 つのスレッドだけがリストにアクセスできます。

オブジェクトを`CMutex`使用するには、必要なときに`CMutex`オブジェクトを構築します。 待機するミューテックスの名前を指定し、アプリケーションが最初に所有するようにします。 コンストラクターが戻ったときにミューテックスにアクセスできます。 制御されたリソースへのアクセスが完了したら[、CSyncObject::ロック解除](../../mfc/reference/csyncobject-class.md#unlock)を呼び出します。

オブジェクトを使用`CMutex`する別の方法として、制御するクラスに`CMutex`データ メンバーとして型の変数を追加します。 制御されたオブジェクトの構築時に、ミューテックスが最初`CMutex`に所有されているかどうかを指定するデータ メンバーのコンストラクター、ミューテックスの名前 (プロセス境界を越えて使用される場合)、および必要なセキュリティ属性を呼び出します。

この方法でオブジェクトによって`CMutex`制御されるリソースにアクセスするには、まず、CSingleLock[CSingleLock](../../mfc/reference/csinglelock-class.md)型の変数を作成するか、リソースのアクセス メンバー関数に[CMultiLock](../../mfc/reference/cmultilock-class.md)型を入力します。 次に、ロック オブジェクトの`Lock`メンバー関数を呼び出します (たとえば[、CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock))。 この時点で、スレッドはリソースへのアクセス権を取得するか、リソースが解放されてアクセスできるようになるのを待つか、リソースが解放されてタイムアウトするまで待機してリソースにアクセスできないかのどちらかです。 いずれの場合も、リソースはスレッド セーフな方法でアクセスされています。 リソースを解放するには、ロック オブジェクトの`Unlock`メンバー関数 ([たとえば、CSingleLock::Unlock)](../../mfc/reference/csinglelock-class.md#unlock)を使用するか、ロック オブジェクトがスコープ外に収まるようにします。

オブジェクトの使用方法`CMutex`の詳細については、「[マルチスレッド : 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmt.h

## <a name="cmutexcmutex"></a><a name="cmutex"></a>Cミューテックス::Cミューテックス

名前付きオブジェクトまたは名前`CMutex`のないオブジェクトを構築します。

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
オブジェクトを作成するスレッドが`CMutex`、ミューテックスによって制御されるリソースに最初にアクセスできるかどうかを指定します。

*名前を指定します。*<br/>
`CMutex` オブジェクトの名前。 同じ名前の別のミューテックスが存在する場合、オブジェクトがプロセス境界を越えて使用される場合は *、lpszName*を指定する必要があります。 **NULL**の場合、ミューテックスは名前なしになります。 名前が既存のミューテックスと一致する場合、コンストラクターは`CMutex`、その名前の mutex を参照する新しいオブジェクトを構築します。 名前がミューテックスではない既存の同期オブジェクトと一致する場合、構築は失敗します。

*属性*<br/>
ミューテックス オブジェクトのセキュリティ属性。 この構造の詳細については、Windows SDK の[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))を参照してください。

### <a name="remarks"></a>解説

`CMutex`オブジェクトにアクセスまたは解放するには[、CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトを作成し、[そのロック](../../mfc/reference/csinglelock-class.md#lock)と[ロック解除](../../mfc/reference/csinglelock-class.md#unlock)のメンバー関数を呼び出します。 オブジェクトが`CMutex`スタンドアロンで使用されている場合は、そのメンバー関数`Unlock`を呼び出して解放します。

> [!IMPORTANT]
> オブジェクトを作成`CMutex`した後[、GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を使用して、ミューテックスが存在していないことを確認します。 ミューテックスが予期せず存在した場合、不正なプロセスがスクワッティングしていることを示している可能性があり、悪意を持ってミューテックスを使用しようとしている可能性があります。 この場合、推奨されるセキュリティ上の問題を意識した手順は、ハンドルを閉じて、オブジェクトの作成に失敗したかのように続行することです。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/csyncobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
