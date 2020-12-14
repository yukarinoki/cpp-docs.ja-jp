---
description: '詳細情報: CCriticalSection クラス'
title: CCriticalSection クラス
ms.date: 11/04/2016
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
ms.openlocfilehash: 0041eea4453ec02159b26805bd5e7a264a410504
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227794"
---
# <a name="ccriticalsection-class"></a>CCriticalSection クラス

"クリティカルセクション" を表します。これは、一度に1つのスレッドがリソースまたはコードセクションにアクセスできるようにする同期オブジェクトです。

## <a name="syntax"></a>構文

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CCriticalSection:: CCriticalSection](#ccriticalsection)|`CCriticalSection` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCriticalSection:: Lock](#lock)|オブジェクトへのアクセスを取得するには、を使用し `CCriticalSection` ます。|
|[CCriticalSection:: Unlock](#unlock)|`CCriticalSection` のオブジェクトを解放します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CCriticalSection:: operator CRITICAL_SECTION *](#operator_critical_section_star)|内部 CRITICAL_SECTION オブジェクトへのポインターを取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CCriticalSection:: m_sect](#m_sect)|CRITICAL_SECTION オブジェクト。|

## <a name="remarks"></a>解説

重要なセクションは、一度に1つのスレッドのみがデータまたはその他の制御されたリソースを変更できるようにする場合に役立ちます。 たとえば、リンクリストへのノードの追加は、一度に1つのスレッドによってのみ許可されるプロセスです。 オブジェクトを使用して `CCriticalSection` リンクリストを制御することにより、一度に1つのスレッドだけがリストにアクセスできます。

> [!NOTE]
> クラスの機能は、 `CCriticalSection` 実際の Win32 CRITICAL_SECTION オブジェクトによって提供されます。

重要なセクションは、mutex の代わりに使用されます (「 [CMutex](../../mfc/reference/cmutex-class.md)」を参照)。速度が重要で、リソースがプロセスの境界を越えて使用されることはありません。

オブジェクトを使用するには、 `CCriticalSection` スタンドアロンでクラスに埋め込まれている2つの方法があります。

- スタンドアロンのオブジェクトを使用するスタンドアロンのメソッド `CCriticalSection` では、 `CCriticalSection` 必要に応じてオブジェクトを構築します。 コンストラクターから正常に返された後、 [ロック](#lock)の呼び出しを使用してオブジェクトを明示的にロックします。 クリティカルセクションへのアクセスが完了したら、 [ロック解除](#unlock) を呼び出します。 このメソッドは、ソースコードを読み取っているユーザーにとってわかりやすくなりますが、アクセスの前後にクリティカルセクションのロックとロック解除を行う必要があるため、エラーが発生しやすくなります。

   より適した方法は、 [CSingleLock](../../mfc/reference/csinglelock-class.md) クラスを使用することです。 また、 `Lock` メソッドとメソッドもあり `Unlock` ますが、例外が発生した場合にリソースのロックを解除する必要はありません。

- 埋め込みメソッド `CCriticalSection` クラスに型のデータメンバーを追加し、必要に応じてデータメンバーをロックすることによって、複数のスレッドでクラスを共有することもできます。

オブジェクトの使用方法の詳細については、 `CCriticalSection` 「 [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>要件

**ヘッダー:** afxmt

## <a name="ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a> CCriticalSection:: CCriticalSection

`CCriticalSection` オブジェクトを構築します。

```
CCriticalSection();
```

### <a name="remarks"></a>解説

オブジェクトにアクセスしたり解放したりするには `CCriticalSection` 、 [CSingleLock](../../mfc/reference/csinglelock-class.md) オブジェクトを作成し、その [Lock](../../mfc/reference/csinglelock-class.md#lock) および [Unlock](../../mfc/reference/csinglelock-class.md#unlock) メンバー関数を呼び出します。 `CCriticalSection`オブジェクトがスタンドアロンで使用されている場合は、その[アンロック](#unlock)メンバー関数を呼び出して解放します。

コンストラクターが必要なシステムメモリの割り当てに失敗した場合は、メモリ例外 (型 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) が自動的にスローされます。

### <a name="example"></a>例

  [CCriticalSection:: Lock](#lock)の例を参照してください。

## <a name="ccriticalsectionlock"></a><a name="lock"></a> CCriticalSection:: Lock

このメンバー関数を呼び出して、クリティカルセクションオブジェクトへのアクセスを取得します。

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>パラメーター

*dwTimeout*<br/>
`Lock` このパラメーター値を無視します。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

`Lock` は、クリティカルセクションオブジェクトが通知される (使用可能になる) まで返されないブロック呼び出しです。

時間指定の待機が必要な場合は、オブジェクトではなく、 [CMutex](../../mfc/reference/cmutex-class.md) オブジェクトを使用でき `CCriticalSection` ます。

が `Lock` 必要なシステムメモリの割り当てに失敗した場合は、メモリ例外 (型 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) が自動的にスローされます。

### <a name="example"></a>例

この例では、共有オブジェクトを使用して共有リソース (静的オブジェクト) へのアクセスを制御することによって、入れ子になったクリティカルセクションのアプローチを示し `_strShared` `CCriticalSection` ます。 関数は、 `SomeMethod` 安全な方法で共有リソースを更新する方法を示しています。

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

## <a name="ccriticalsectionm_sect"></a><a name="m_sect"></a> CCriticalSection:: m_sect

すべてのメソッドで使用されるクリティカルセクションオブジェクトを格納 `CCriticalSection` します。

```
CRITICAL_SECTION m_sect;
```

## <a name="ccriticalsectionoperator-critical_section"></a><a name="operator_critical_section_star"></a> CCriticalSection:: operator CRITICAL_SECTION *

CRITICAL_SECTION オブジェクトを取得します。

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>解説

内部 CRITICAL_SECTION オブジェクトへのポインターを取得するには、この関数を呼び出します。

## <a name="ccriticalsectionunlock"></a><a name="unlock"></a> CCriticalSection:: Unlock

別の `CCriticalSection` スレッドによって使用されるようにオブジェクトを解放します。

```
BOOL Unlock();
```

### <a name="return-value"></a>戻り値

`CCriticalSection`オブジェクトがスレッドによって所有されていて、リリースが成功した場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>解説

`CCriticalSection`がスタンドアロンで使用されている場合は、 `Unlock` クリティカルセクションによって制御されるリソースの使用が完了した直後に、を呼び出す必要があります。 [CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトが使用されている場合、 `CCriticalSection::Unlock` はロックオブジェクトのメンバー関数によって呼び出され `Unlock` ます。

### <a name="example"></a>例

  [CCriticalSection:: Lock](#lock)の例を参照してください。

## <a name="see-also"></a>関連項目

[CSyncObject クラス](../../mfc/reference/csyncobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CMutex クラス](../../mfc/reference/cmutex-class.md)
