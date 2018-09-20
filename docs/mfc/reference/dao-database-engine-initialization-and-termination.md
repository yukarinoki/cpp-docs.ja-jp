---
title: DAO データベース エンジンの初期化と終了 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8cf54992896559f1b143247746ef9f9e0e8d8979
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404008"
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

### <a name="requirements"></a>要件

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

### <a name="requirements"></a>要件

  **ヘッダー** afxdao.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
