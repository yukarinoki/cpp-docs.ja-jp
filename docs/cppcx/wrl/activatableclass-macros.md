---
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
ms.openlocfilehash: 7bc3d789d6c0d304aa170d59dff23a97a67061d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214278"
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

`#undef` ディレクティブを使用して `__WRL_WINRT_STRICT__` マクロ定義が削除されるようにしない限り、これらのマクロは従来の COM では使用しないでください。

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Module クラス](module-class.md)
