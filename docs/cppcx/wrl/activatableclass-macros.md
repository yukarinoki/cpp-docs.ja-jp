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
ms.openlocfilehash: eee8267e2e76eead267eb2486836dbcc38a90231
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785483"
---
# <a name="activatableclass-macros"></a>ActivatableClass マクロ

指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを設定します。

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
作成するクラスの名前です。

*ファクトリ*<br/>
指定したクラスのインスタンスを作成するファクトリ。

*serverName*<br/>
モジュールのファクトリのサブセットを指定する名前。

## <a name="remarks"></a>Remarks

これらのマクロで使わないクラシック COM を使用しない限り、`#undef`ことを確認するディレクティブ、`__WRL_WINRT_STRICT__`マクロ定義が削除されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** module.h

**名前空間:** Microsoft::wrl

## <a name="see-also"></a>関連項目

[Module クラス](module-class.md)