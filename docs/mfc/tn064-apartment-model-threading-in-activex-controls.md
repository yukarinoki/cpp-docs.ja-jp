---
title: TN064:アパートメント モデルの ActiveX コントロールにおけるスレッド処理
ms.date: 11/04/2016
f1_keywords:
- vc.controls.activex
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
ms.openlocfilehash: d6f02b2106693226f6380e935a54e04e10d5b4f8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351827"
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>TN064:アパートメント モデルの ActiveX コントロールにおけるスレッド処理

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このテクニカル ノートでは、ActiveX コントロールにおけるアパートメント モデルのスレッドを有効にする方法について説明します。 Visual C バージョン 4.2 以降でスレッドのアパートメント モデルをサポートのみに注意してください。

## <a name="what-is-apartment-model-threading"></a>アパートメント モデルのスレッドとは

アパートメント モデルは、マルチ コンテナー アプリケーション内での ActiveX コントロールなどの埋め込みオブジェクトをサポートするアプローチです。 アプリケーションには、複数のスレッドがありますが、1 つ"のアパートメントに、"1 つのスレッドで実行されますが、埋め込みオブジェクトの各インスタンスが割り当てられます。 つまり、コントロールのインスタンスにすべての呼び出しは、同じスレッドで実行されます。

ただし、同じ種類のコントロールの複数のインスタンスを異なるアパートメントに割り当てることができます。 そのため、コントロールの複数のインスタンスは、一般的な (たとえば、グローバルまたは静的データ) 内のデータを共有している場合は、この共有データへのアクセスがクリティカル セクションなどの同期オブジェクトで保護する必要があります。

詳細については、アパートメント スレッド モデルを参照してください[プロセスとスレッド](/windows/desktop/ProcThread/processes-and-threads)で、 *OLE プログラマーズ リファレンス*します。

## <a name="why-support-apartment-model-threading"></a>アパートメント モデルのスレッドをサポートする理由

アパートメント モデルのスレッドをサポートするコントロールは、アパートメント モデルをサポートするマルチ コンテナー アプリケーションで使用できます。 アパートメント モデルのスレッドを有効にしない場合は、コントロールを使用される可能性がありますコンテナーの潜在的なセットが制限されます。

アパートメント モデルのスレッドを有効にすることはほとんどまたはまったくの共有データがある場合に特に多くのコントロールでは簡単です。

## <a name="protecting-shared-data"></a>共有データの保護

コントロールが共有のデータを使用している場合など、静的メンバー変数へのアクセスを 1 つ以上のスレッドが同時にデータを変更することを防ぐために重要なセクションにデータを保護する必要があります。 このため、クリティカル セクションを設定するクラスの静的メンバー変数を宣言`CCriticalSection`コントロールのクラス。 使用して、`Lock`と`Unlock`このクリティカル セクションのメンバー関数は、コード共有のデータにアクセスするオブジェクトします。

たとえば、すべてのインスタンスによって共有されている文字列を管理する必要があるコントロール クラスを検討します。 この文字列は、静的メンバー変数内に保持およびクリティカル セクションによって保護されていることができます。 コントロールのクラス宣言は、次が含まれます。

```
class CSampleCtrl : public COleControl
{
...
    static CString _strShared;
    static CCriticalSection _critSect;
};
```

このクラスの実装には、これらの変数の定義が含まれます。

```
int CString CSampleCtrl::_strShared;
CCriticalSection CSampleCtrl::_critSect;
```

アクセス、`_strShared`静的メンバーは、クリティカル セクションによって保護されます。

```
void CSampleCtrl::SomeMethod()
{
    _critSect.Lock();
if (_strShared.Empty())
    _strShared = "<text>";
    _critSect.Unlock();

...
}
```

## <a name="registering-an-apartment-model-aware-control"></a>アパートメント モデル対応のコントロールの登録

アパートメント モデルのスレッドをサポートするコントロールは、クラスの ID のレジストリ エントリの下で「アパートメント」の値を持つ"ThreadingModel"名前付きの値を追加することで、レジストリでこの機能を指定する必要があります、*クラス id* \\ **InprocServer32**キー。 コントロールに自動的に登録するには、このキーには、渡す、 *afxRegApartmentThreading* 6 番目のパラメーターでフラグ`AfxOleRegisterControlClass`:

```
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

コントロール プロジェクトは、ControlWizard 4.1 またはそれ以降のバージョンの Visual c で生成された場合、このフラグは、コードで存在でしょう。 変更するスレッド処理モデルを登録する必要はありません。

プロジェクトは、以前のバージョンの ControlWizard によって生成された、既存のコードは、6 番目のパラメーターとしてブール値があります。 既存のパラメーターが TRUE の場合は変更して*afxRegInsertable | afxRegApartmentThreading*します。 既存のパラメーターが FALSE の場合は、変更して*afxRegApartmentThreading*します。

渡す必要がありますいない場合は、コントロールは、アパートメント モデルのスレッドの規則に従っていない、 *afxRegApartmentThreading*このパラメーターにします。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
