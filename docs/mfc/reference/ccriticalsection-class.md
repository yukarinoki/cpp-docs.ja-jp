---
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
ms.openlocfilehash: d79199a332f6930619e6b4995b04bc590b6ea580
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369362"
---
# <a name="ccriticalsection-class"></a>CCriticalSection クラス

"クリティカル セクション" を表します— 一度に 1 つのスレッドがリソースまたはコードのセクションにアクセスできるようにする同期オブジェクト。

## <a name="syntax"></a>構文

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[クリティカルセクション::クリティカルセクション](#ccriticalsection)|`CCriticalSection` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クリティカルセクション::ロック](#lock)|`CCriticalSection`オブジェクトにアクセスするために使用します。|
|[クリティカルセクション::ロック解除](#unlock)|`CCriticalSection` のオブジェクトを解放します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[クリティカルセクション::オペレーターCRITICAL_SECTION*](#operator_critical_section_star)|内部CRITICAL_SECTION オブジェクトへのポインターを取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[危機的なセクション::m_sect](#m_sect)|CRITICAL_SECTIONオブジェクト。|

## <a name="remarks"></a>解説

クリティカル セクションは、一度に 1 つのスレッドだけがデータやその他の制御されたリソースを変更できる場合に役立ちます。 たとえば、リンク リストにノードを追加するプロセスは、一度に 1 つのスレッドだけが許可する必要があります。 オブジェクトを`CCriticalSection`使用してリンク リストを制御すると、一度に 1 つのスレッドだけがリストにアクセスできます。

> [!NOTE]
> クラスの`CCriticalSection`機能は、実際の Win32 CRITICAL_SECTION オブジェクトによって提供されます。

速度が重要で、リソースがプロセス境界を越えて使用されない場合、ミューテックスの代わりにクリティカル セクションが使用されます[(CMutex](../../mfc/reference/cmutex-class.md)を参照)。

`CCriticalSection`オブジェクトを使用する方法には、スタンドアロンとクラスに埋め込まれる 2 つのメソッドがあります。

- スタンドアロン メソッド スタンドアロン`CCriticalSection`オブジェクトを使用するには、必要なときにオブジェクト`CCriticalSection`を構築します。 コンストラクターから正常に戻った後[、Lock](#lock)の呼び出しでオブジェクトを明示的にロックします。 クリティカル セクションへのアクセスが完了したら[、Unlock](#unlock)を呼び出します。 この方法は、ソースコードを読んでいる人にとって明確ですが、アクセスの前後にクリティカルセクションをロックおよびロック解除することを忘れないようにする必要があります。

   より望ましい方法は[、CSingleLock](../../mfc/reference/csinglelock-class.md)クラスを使用することです。 また、`Lock`メソッドと`Unlock`メソッドもありますが、例外が発生した場合にリソースのロックを解除する必要はありません。

- 埋め込みメソッド -type データ メンバーをクラス`CCriticalSection`に追加し、必要に応じてデータ メンバーをロックすることで、クラスを複数のスレッドと共有することもできます。

オブジェクトの使用方法`CCriticalSection`の詳細については、「[マルチスレッド : 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmt.h

## <a name="ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a>クリティカルセクション::クリティカルセクション

`CCriticalSection` オブジェクトを構築します。

```
CCriticalSection();
```

### <a name="remarks"></a>解説

`CCriticalSection`オブジェクトにアクセスまたは解放するには[、CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトを作成し、[そのロック](../../mfc/reference/csinglelock-class.md#lock)と[ロック解除](../../mfc/reference/csinglelock-class.md#unlock)のメンバー関数を呼び出します。 オブジェクトが`CCriticalSection`スタンドアロンで使用されている場合は[、Unlock](#unlock)メンバー関数を呼び出して解放します。

コンストラクタが必要なシステム メモリの割り当てに失敗した場合[、(CMemoryException](../../mfc/reference/cmemoryexception-class.md)型の) メモリ例外が自動的にスローされます。

### <a name="example"></a>例

  [「CCriticalSection::Lock」](#lock)の例を参照してください。

## <a name="ccriticalsectionlock"></a><a name="lock"></a>クリティカルセクション::ロック

クリティカル セクション オブジェクトにアクセスするには、このメンバー関数を呼び出します。

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>パラメーター

*タイムアウト*<br/>
`Lock`このパラメータ値は無視されます。

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

`Lock`は、クリティカル セクション オブジェクトがシグナル状態になるまで戻らないブロッキング呼び出しです (使用可能になります)。

時間指定待機が必要な場合は、オブジェクトの代わりに[CMutex](../../mfc/reference/cmutex-class.md) `CCriticalSection`オブジェクトを使用できます。

必要`Lock`なシステム メモリの割り当てに失敗した場合は[、(CMemoryException](../../mfc/reference/cmemoryexception-class.md)型の) メモリ例外が自動的にスローされます。

### <a name="example"></a>例

この例では、共有`_strShared``CCriticalSection`オブジェクトを使用して共有リソース (静的オブジェクト) へのアクセスを制御することにより、入れ子になったクリティカル セクションのアプローチを示します。 この`SomeMethod`関数は、共有リソースを安全に更新する方法を示します。

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

## <a name="ccriticalsectionm_sect"></a><a name="m_sect"></a>危機的なセクション::m_sect

すべての`CCriticalSection`メソッドで使用されるクリティカル セクション オブジェクトを含みます。

```
CRITICAL_SECTION m_sect;
```

## <a name="ccriticalsectionoperator-critical_section"></a><a name="operator_critical_section_star"></a>クリティカルセクション::オペレーターCRITICAL_SECTION*

CRITICAL_SECTION オブジェクトを取得します。

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>解説

内部CRITICAL_SECTION オブジェクトへのポインターを取得します。

## <a name="ccriticalsectionunlock"></a><a name="unlock"></a>クリティカルセクション::ロック解除

別の`CCriticalSection`スレッドで使用するオブジェクトを解放します。

```
BOOL Unlock();
```

### <a name="return-value"></a>戻り値

オブジェクトが`CCriticalSection`スレッドによって所有され、解放が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

がスタンドアロン`CCriticalSection`で使用されている場合は、`Unlock`クリティカル セクションによって制御されるリソースの使用が完了した直後に呼び出す必要があります。 [CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトが使用されている場合は`CCriticalSection::Unlock`、ロック オブジェクトの`Unlock`メンバー関数によって呼び出されます。

### <a name="example"></a>例

  [「CCriticalSection::Lock」](#lock)の例を参照してください。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/csyncobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CMutex クラス](../../mfc/reference/cmutex-class.md)
