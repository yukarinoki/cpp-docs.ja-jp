---
title: DAO データベース エンジンの初期化と終了
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: ccdf2e7b0f31576dddccad016e6b32806cdb82bf
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095886"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了

DAO は Access データベースで使用され、Office 2013 でサポートされています。 3.6 は最終バージョンであり、廃止されたと見なされます。 MFC DAO オブジェクトを使用する場合は、アプリケーションまたは DLL を終了する前に、最初に DAO データベースエンジンを初期化して終了する必要があります。 `AfxDaoInit` と`AfxDaoTerm`の2つの関数は、これらのタスクを実行します。

### <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了

|||
|-|-|
|[AfxDaoInit](#afxdaoinit)|DAO データベースエンジンを初期化します。|
|[AfxDaoTerm](#afxdaoterm)|DAO データベースエンジンを終了します。|

##  <a name="afxdaoinit"></a>AfxDaoInit

この関数は、DAO データベースエンジンを初期化します。

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Remarks

ほとんどの場合、アプリケーションが必要に応じ`AfxDaoInit`て自動的に呼び出すため、を呼び出す必要はありません。

関連情報、およびの呼び出し`AfxDaoInit`の例については、「[テクニカルノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao

##  <a name="afxdaoterm"></a>AfxDaoTerm

この関数は、DAO データベースエンジンを終了します。

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Remarks

通常、この関数を呼び出す必要があるのは、通常の MFC DLL の場合だけです。アプリケーションは、必要な`AfxDaoTerm`ときに自動的にを呼び出します。

通常の mfc dll では`AfxDaoTerm` 、関数`ExitInstance`の前にを呼び出しますが、すべての mfc DAO オブジェクトが破棄された後にを呼び出します。

関連情報については、「[テクニカルノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
