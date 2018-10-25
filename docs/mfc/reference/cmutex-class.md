---
title: CMutex クラス |Microsoft Docs
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
ms.openlocfilehash: 23270275103faac3af48a3627a5f5833140645e2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066747"
---
# <a name="cmutex-class"></a>CMutex クラス

「ミュー テックス」を表します: リソースへの 1 つのスレッド相互に排他的アクセスを許可する同期オブジェクト。

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

ミュー テックスは、データまたはその他の制御されたリソースの変更を一度に 1 つのスレッドができる場合に便利です。 たとえば、リンク リスト ノードの追加は、一度に 1 つのスレッドでのみ許可するプロセスです。 使用して、`CMutex`だけで、一覧に、一度に 1 つのスレッドがアクセスできるリンクのリストを制御するオブジェクト。

使用する、`CMutex`オブジェクト、構築、`CMutex`必要がある場合のオブジェクトします。 待機、ミュー テックスの名前を指定し、アプリケーションが最初に所有する必要があります。 コンス トラクターは、返されるときにミュー テックスをアクセスできます。 呼び出す[したら](../../mfc/reference/csyncobject-class.md#unlock)が終わったら、被制御リソースにアクセスします。

代替の方法を使用して`CMutex`オブジェクトは、型の変数を追加する`CMutex`を制御するクラスにデータ メンバーとして。 コンス トラクターを呼び出し、制御されるオブジェクトの構築時に、`CMutex`ミュー テックスが最初に所有する、ミュー テックスの名前 (プロセスの境界を越えて使用) 場合、およびセキュリティ属性を必要なかどうかに指定するデータ メンバー。

によって制御されるリソースにアクセスする`CMutex`オブジェクトが、この方法では、いずれかの型の変数をまず作成[CSingleLock](../../mfc/reference/csinglelock-class.md)または型[CMultiLock](../../mfc/reference/cmultilock-class.md)リソースのアクセス メンバー関数。 呼び出して、ロック オブジェクトの`Lock`メンバー関数 (たとえば、 [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock))。 この時点では、スレッドはいずれか、リソースにアクセスを待機してから、リソースを解放して、アクセスを取得またはリソースが解放されると、リソースへのアクセスに失敗したときのタイムアウトを待ちます。 いずれの場合も、リソースがスレッド セーフな方法でアクセスされました。 リソースを解放するロック オブジェクトを使用して、`Unlock`メンバー関数 (たとえば、 [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock))、またはロック オブジェクトがスコープから除外できるようにします。

使用しての詳細については`CMutex`オブジェクトは、記事をご覧ください。[マルチ スレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmt.h

##  <a name="cmutex"></a>  CMutex::CMutex

名前付きセーブポイントまたは名前のない、コンストラクト`CMutex`オブジェクト。

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>パラメーター

*bInitiallyOwn*<br/>
場合を指定します、スレッドを作成する、`CMutex`オブジェクトが最初に、ミュー テックスによって制御されるリソースへのアクセスを持ちます。

*lpszName*<br/>
`CMutex` オブジェクトの名前。 同じ名前の別のミュー テックスが存在する場合、 *lpszName*プロセスの境界を越えてオブジェクトを使用する場合に指定する必要があります。 場合**NULL**、ミュー テックスは名前付きできません。 名前が既存のミュー テックスに一致する場合、コンス トラクターは新しい`CMutex`その名前のミュー テックスを参照するオブジェクト。 名前には、ミュー テックスではない既存の同期オブジェクトが一致すると、構築は失敗します。

*lpsaAttribute*<br/>
ミュー テックス オブジェクトのセキュリティ属性。 この構造体の詳細については、次を参照してください。 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK に含まれています。

### <a name="remarks"></a>Remarks

アクセスまたはリリースを`CMutex`オブジェクトを作成、 [CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトと呼び出しの[ロック](../../mfc/reference/csinglelock-class.md#lock)と[Unlock](../../mfc/reference/csinglelock-class.md#unlock)メンバー関数。 場合、`CMutex`オブジェクトがスタンドアロンの使用にされている場合、呼び出しの`Unlock`メンバー関数は、それを解放します。

> [!IMPORTANT]
>  作成した後、`CMutex`オブジェクトを使用して[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)ミュー テックスがまだ存在しないことを確認します。 予期せずにミュー テックスが存在して、不正なプロセスが発生したり、悪意のあるミュー テックスを使用するつもりが可能性があります。 ここでは、セキュリティ意識の推奨手順は、ハンドルを終了し、クリックすると、オブジェクトの作成でエラーが発生しました。

## <a name="see-also"></a>関連項目

[CSyncObject クラス](../../mfc/reference/csyncobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)

