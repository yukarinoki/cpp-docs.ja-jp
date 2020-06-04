---
title: DAO データベース エンジンの初期化と終了
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 62460e8e55f70b8cb0743f1d044636d25121050d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365893"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了

DAO は Access データベースで使用され、Office 2013 を通じてサポートされます。 DAO 3.6 は最終バージョンであり、廃止と見なされます。 MFC DAO オブジェクトを使用する場合は、アプリケーションまたは DLL が終了する前に、DAO データベース エンジンを初期化してから終了する必要があります。 2 つの`AfxDaoInit`関数`AfxDaoTerm`と、 の 2 つのタスクを実行します。

### <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了

|||
|-|-|
|[AfxDaoInit](#afxdaoinit)|DAO データベース エンジンを初期化します。|
|[AfxDaoTerm](#afxdaoterm)|DAO データベース エンジンを終了します。|

## <a name="afxdaoinit"></a><a name="afxdaoinit"></a>アズダオイニト

この関数は、DAO データベース エンジンを初期化します。

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>解説

ほとんどの場合、必要なときにアプリケーションが自動的に呼び`AfxDaoInit`出すため、呼び出す必要はありません。

関連情報および 呼び出し`AfxDaoInit`の例については、[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="afxdaoterm"></a><a name="afxdaoterm"></a>アズダオターム

この関数は、DAO データベース エンジンを終了します。

```

void AfxDaoTerm();
```

### <a name="remarks"></a>解説

通常、この関数は通常の MFC DLL でのみ呼び出す必要があります。必要な場合は、`AfxDaoTerm`アプリケーションが自動的に呼び出されます。

通常の MFC DLL`AfxDaoTerm`では、`ExitInstance`関数の前に呼び出しますが、すべての MFC DAO オブジェクトが破棄された後に呼び出します。

関連情報については、[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
