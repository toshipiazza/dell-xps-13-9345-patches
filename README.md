# Dell XPS 13 9345 TPM patches

This repo contains a couple of patches against the Linux kernel for the Dell XPS 13 9345 (and possibly other devices powered by the Snapdragon X Elite).

The tpm driver patch adds a driver for the qcom.tz.tpm applet and makes it available over /dev/tpm0. You can interact with this tpm using the standard `tpm2-tools`. On the Dell XPS 13 9345, this applet will passthrough to a discrete TPM.

The uefi-log patch reads the UEFI log from reserved-memory specified in the device tree and makes it available to /sys/kernel/debug/uefi-log. Note that there is no standardized format here, it's just a text file with some debug logging from pre-UEFI and UEFI components. This patch can be applied separately, and is not particularly interesting.

Patches are successfully applied against the following branches of Ubuntu questing (25.10):

* [Ubuntu-6.17.0-5.5](https://git.launchpad.net/~ubuntu-kernel/ubuntu/+source/linux/+git/questing/tag/?h=Ubuntu-6.17.0-5.5)
* [Ubuntu-6.17.0-6.6](https://git.launchpad.net/~ubuntu-kernel/ubuntu/+source/linux/+git/questing/tag/?h=Ubuntu-6.17.0-6.6)
* [qcom-x1e-6.18](https://git.launchpad.net/~ubuntu-concept/ubuntu/+source/linux/+git/questing/log/?h=qcom-x1e-6.18)
