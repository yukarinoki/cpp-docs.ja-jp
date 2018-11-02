---
title: DAO データベース エンジンの初期化と終了
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.data
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: ff924f0e0d599d447ef7dea0039de788d388d759
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589632"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了

MFC DAO オブジェクトを使用する場合、DAO データベース エンジンは、最初に初期化され、終了し、アプリケーションまたは DLL が終了する前にします。 2 つの関数、`AfxDaoInit`と`AfxDaoTerm`、これらのタスクを実行します。

### <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了

|||
|-|-|
|[AfxDaoInit](#afxdaoinit)|DAO データベース エンジンを初期化します。|
|[AfxDaoTerm](#afxdaoterm)|DAO データベース エンジンを終了します。|

##  <a name="afxdaoinit"></a>  AfxDaoInit

この関数では、DAO データベース エンジンを初期化します。

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Remarks

ほとんどの場合を呼び出す必要はありません`AfxDaoInit`必要なアプリケーションが自動的に呼び出すためです。

呼び出し元の例については、関連情報については、`AfxDaoInit`を参照してください[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

##  <a name="afxdaoterm"></a>  AfxDaoTerm

この関数は、データベース エンジンの初期化を終了します。

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Remarks

通常、だけで済みますレギュラー MFC DLL; でこの関数を呼び出すアプリケーションが自動的に呼び出さ`AfxDaoTerm`が必要です。

レギュラー MFC Dll を呼び出す`AfxDaoTerm`する前に、`ExitInstance`関数が、すべての MFC DAO オブジェクトが破棄された後にします。

関連情報については、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdao.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
