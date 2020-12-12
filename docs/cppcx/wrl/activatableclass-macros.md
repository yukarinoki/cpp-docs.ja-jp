---
description: '詳細情報: ActivatableClass マクロ'
title: ActivatableClass マクロ
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
ms.openlocfilehash: 2b59101373de72ca88338750bb7fe9169376ac65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287945"
---
# <a name="activatableclass-macros"></a>ActivatableClass マクロ

指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを作成します。

## <a name="syntax"></a>構文

```cpp
ActivatableClass(
   className
);

ActivatableClassWithFactory(
   className,
   factory
);

ActivatableClassWithFactoryEx(
   className,
   factory,
   serverName
);
```

### <a name="parameters"></a>パラメーター

*className*<br/>
作成するクラスの名前。

*factory*<br/>
指定されたクラスのインスタンスを作成するファクトリ。

*serverName*<br/>
モジュール内のファクトリのサブセットを指定する名前。

## <a name="remarks"></a>解説

`#undef`マクロ定義が削除されるようにディレクティブを使用する場合を除き、これらのマクロは従来の COM では使用しないでください `__WRL_WINRT_STRICT__` 。

## <a name="requirements"></a>要件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Module クラス](module-class.md)
