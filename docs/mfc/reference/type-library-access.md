---
title: タイプ ライブラリ アクセス
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 1794e16489ab48d919bbd4116588fba4b74b88d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372875"
---
# <a name="type-library-access"></a>タイプ ライブラリ アクセス

タイプ ライブラリは、OLE コントロールのインターフェイスを他の OLE 対応アプリケーションに公開します。 1 つ以上のインターフェイスを公開する場合は、各 OLE コントロールにタイプ ライブラリが必要です。

次のマクロを使用すると、OLE コントロールは独自のタイプ ライブラリにアクセスできます。

### <a name="type-library-access"></a>タイプ ライブラリ アクセス

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|OLE コントロール`GetTypeLib`のメンバー関数を宣言します 。|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|OLE コントロール`GetTypeLib`のメンバー関数を実装します 。|

## <a name="declare_oletypelib"></a><a name="declare_oletypelib"></a>DECLARE_OLETYPELIB

コントロール クラス`GetTypeLib`のメンバー関数を宣言します。

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
タイプ ライブラリに関連するコントロール クラスの名前。

### <a name="remarks"></a>解説

このマクロは、コントロール クラスヘッダー ファイルで使用します。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="implement_oletypelib"></a><a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB

コントロールのメンバー関数を`GetTypeLib`実装します。

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
タイプ ライブラリに関連するコントロール クラスの名前。

*トリッド*<br/>
タイプ ライブラリの ID 番号。

*wVerメジャー*<br/>
タイプ ライブラリのメジャー バージョン番号。

*wVerMinor*<br/>
タイプ ライブラリのマイナー バージョン番号。

### <a name="remarks"></a>解説

このマクロは、DECLARE_OLETYPELIB マクロを使用するコントロール クラスの実装ファイルに含める必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
