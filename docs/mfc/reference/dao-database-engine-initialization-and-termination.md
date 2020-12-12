---
description: 詳細については、「DAO データベースエンジンの初期化と終了」を参照してください。
title: DAO データベース エンジンの初期化と終了
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 9e9b522d744eabc84074b201051151b80ed75d7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220397"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了

DAO は Access データベースで使用され、Office 2013 でサポートされています。 DAO 3.6 は最終バージョンであり、互換性のために残されているものと見なされます。 MFC DAO オブジェクトを使用する場合は、アプリケーションまたは DLL を終了する前に、最初に DAO データベースエンジンを初期化して終了する必要があります。 との2つの関数は、 `AfxDaoInit` `AfxDaoTerm` これらのタスクを実行します。

### <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了

|名前|説明|
|-|-|
|[AfxDaoInit](#afxdaoinit)|DAO データベースエンジンを初期化します。|
|[AfxDaoTerm](#afxdaoterm)|DAO データベースエンジンを終了します。|

## <a name="afxdaoinit"></a><a name="afxdaoinit"></a> AfxDaoInit

この関数は、DAO データベースエンジンを初期化します。

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>解説

ほとんどの場合、 `AfxDaoInit` アプリケーションが必要に応じて自動的に呼び出すため、を呼び出す必要はありません。

関連情報、およびの呼び出しの例につい `AfxDaoInit` ては、「 [テクニカルノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdao

## <a name="afxdaoterm"></a><a name="afxdaoterm"></a> AfxDaoTerm

この関数は、DAO データベースエンジンを終了します。

```

void AfxDaoTerm();
```

### <a name="remarks"></a>解説

通常、この関数を呼び出す必要があるのは、通常の MFC DLL の場合だけです。アプリケーションは、必要なときに自動的にを呼び出し `AfxDaoTerm` ます。

通常の MFC Dll では、 `AfxDaoTerm` 関数の前にを呼び出し `ExitInstance` ますが、すべての mfc DAO オブジェクトが破棄された後にを呼び出します。

関連情報については、「 [テクニカルノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdao

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
