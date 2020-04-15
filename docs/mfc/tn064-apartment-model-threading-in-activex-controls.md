---
title: 'テクニカル ノート 64: ActiveX コントロールにおけるアパートメント モデルのスレッド処理'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
ms.openlocfilehash: 0c6a42124b4b2b03ae7cd9277fa14d43eac7a2bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366071"
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>テクニカル ノート 64: ActiveX コントロールにおけるアパートメント モデルのスレッド処理

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このテクニカル ノートでは、ActiveX コントロールでアパートメント モデルのスレッド処理を有効にする方法について説明します。 アパートメント モデルのスレッド処理は、Visual C++ バージョン 4.2 以降でのみサポートされることに注意してください。

## <a name="what-is-apartment-model-threading"></a>アパートモデルのスレッドとは

アパートメント モデルは、マルチスレッド コンテナー アプリケーション内で ActiveX コントロールなどの埋め込みオブジェクトをサポートするためのアプローチです。 アプリケーションには複数のスレッドを持つ場合がありますが、埋め込みオブジェクトの各インスタンスは 1 つの "アパートメント" に割り当てられ、1 つのスレッドでのみ実行されます。 つまり、コントロールのインスタンスに対するすべての呼び出しは、同じスレッドで発生します。

ただし、同じタイプのコントロールの異なるインスタンスは、異なるアパートメントに割り当てることができます。 したがって、コントロールの複数のインスタンスが共通のデータ (たとえば、静的データやグローバル データ) を共有する場合、この共有データへのアクセスは、クリティカル セクションなどの同期オブジェクトによって保護される必要があります。

アパートメント スレッド モデルの詳細については、 *OLE プログラマ*リファレンス[のプロセスとスレッド](/windows/win32/ProcThread/processes-and-threads)を参照してください。

## <a name="why-support-apartment-model-threading"></a>なぜアパートモデルのスレッドをサポート

アパートメント モデルのスレッド処理をサポートするコントロールは、アパートメント モデルもサポートするマルチスレッド コンテナー アプリケーションで使用できます。 アパートメント モデルのスレッド処理を有効にしないと、コントロールを使用できるコンテナのセットが制限されます。

アパートメント モデルのスレッド処理を有効にすると、ほとんどのコントロールで簡単に、共有データがほとんどまたはまったくない場合に使用できます。

## <a name="protecting-shared-data"></a>共有データの保護

静的メンバー変数などの共有データをコントロールで使用する場合、複数のスレッドが同時にデータを変更できないように、そのデータへのアクセスをクリティカル セクションで保護する必要があります。 この目的のためにクリティカル セクションを設定するには、コントロールのクラスでクラス`CCriticalSection`の静的メンバー変数を宣言します。 このクリティカル`Lock``Unlock`セクション オブジェクトの と メンバー関数は、共有データにアクセスするコードの場合はいつでも使用します。

たとえば、すべてのインスタンスで共有される文字列を保持する必要があるコントロール クラスを考えてみます。 この文字列は、静的メンバー変数内で維持され、クリティカル セクションによって保護されます。 コントロールのクラス宣言には、次の内容が含まれます。

```cpp
class CSampleCtrl : public COleControl
{
...
    static CString _strShared;
    static CCriticalSection _critSect;
};
```

クラスの実装には、次の変数の定義が含まれます。

```cpp
int CString CSampleCtrl::_strShared;
CCriticalSection CSampleCtrl::_critSect;
```

`_strShared`静的メンバーへのアクセスは、クリティカル セクションによって保護できます。

```cpp
void CSampleCtrl::SomeMethod()
{
    _critSect.Lock();
if (_strShared.Empty())
    _strShared = "<text>";
    _critSect.Unlock();

...
}
```

## <a name="registering-an-apartment-model-aware-control"></a>アパートメント モデル対応コントロールの登録

アパートメント モデルのスレッド処理をサポートするコントロールは、*クラス id*\\**InprocServer32**キーの下のクラス ID レジストリ エントリに "アパートメント" の値を持つ名前付き値 "ThreadingModel" を追加することにより、レジストリでこの機能を示す必要があります。 コントロールに対してこのキーを自動的に登録するには、6 番目のパラメーターの*afxRegApartmentThreading* `AfxOleRegisterControlClass`フラグを渡します。

```cpp
BOOL CSampleCtrl::CSampleCtrlFactory::UpdateRegistry(BOOL bRegister)
{
    if (bRegister)
    return AfxOleRegisterControlClass(
    AfxGetInstanceHandle(),
    m_clsid,
    m_lpszProgID,
    IDS_SAMPLE,
    IDB_SAMPLE,
    afxRegApartmentThreading,
    _dwSampleOleMisc,
    _tlid,
    _wVerMajor,
    _wVerMinor);

else
    return AfxOleUnregisterClass(m_clsid,
    m_lpszProgID);

}
```

Visual C++ バージョン 4.1 以降の ControlWizard によってコントロール プロジェクトが生成された場合、このフラグは既にコード内に存在します。 スレッド モデルを登録するために変更は必要ありません。

プロジェクトが以前のバージョンの ControlWizard によって生成された場合、既存のコードには 6 番目のパラメーターとしてブール値が設定されます。 既存のパラメーターが TRUE の場合は、*それを afxReg 挿入可能 | afxRegApartment スレッドに変更します*。 既存のパラメーターが FALSE の場合は、*それを afxRegApartmentThreading*に変更します。

コントロールがアパートメント モデルスレッドの規則に従っていない場合は、このパラメーターで*afxRegApartmentThreading を*渡してはなりません。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
