workspace(name = "kubevirt")

load("//third_party:deps.bzl", "deps")

deps()

# register crosscompiler toolchains
load("//bazel/toolchain:toolchain.bzl", "register_all_toolchains")

register_all_toolchains()

load(
    "@bazel_tools//tools/build_defs/repo:http.bzl",
    "http_archive",
    "http_file",
)
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

http_archive(
    name = "rules_python",
    sha256 = "934c9ceb552e84577b0faf1e5a2f0450314985b4d8712b2b70717dc679fdc01b",
    urls = [
        "https://github.com/bazelbuild/rules_python/releases/download/0.3.0/rules_python-0.3.0.tar.gz",
        "https://storage.googleapis.com/builddeps/934c9ceb552e84577b0faf1e5a2f0450314985b4d8712b2b70717dc679fdc01b",
    ],
)

# Additional bazel rules
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_proto",
    sha256 = "bc12122a5ae4b517fa423ea03a8d82ea6352d5127ea48cb54bc324e8ab78493c",
    strip_prefix = "rules_proto-af6481970a34554c6942d993e194a9aed7987780",
    urls = [
        "https://github.com/bazelbuild/rules_proto/archive/af6481970a34554c6942d993e194a9aed7987780.tar.gz",
        "https://storage.googleapis.com/builddeps/bc12122a5ae4b517fa423ea03a8d82ea6352d5127ea48cb54bc324e8ab78493c",
    ],
)

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")

rules_proto_dependencies()

rules_proto_toolchains()

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "099a9fb96a376ccbbb7d291ed4ecbdfd42f6bc822ab77ae6f1b5cb9e914e94fa",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/v0.35.0/rules_go-v0.35.0.zip",
        "https://github.com/bazelbuild/rules_go/releases/download/v0.35.0/rules_go-v0.35.0.zip",
        "https://storage.googleapis.com/builddeps/099a9fb96a376ccbbb7d291ed4ecbdfd42f6bc822ab77ae6f1b5cb9e914e94fa",
    ],
)

# XXX: For now stick with 0.24. The resultion mode changed from 'external' to 'static' which causes some import troubles.
# See https://github.com/bazelbuild/bazel-gazelle/pull/1264#issuecomment-1288680264 for details. Can be resolved at some point.
http_archive(
    name = "bazel_gazelle",
    sha256 = "de69a09dc70417580aabf20a28619bb3ef60d038470c7cf8442fafcf627c21cb",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-gazelle/releases/download/v0.24.0/bazel-gazelle-v0.24.0.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/v0.24.0/bazel-gazelle-v0.24.0.tar.gz",
        "https://storage.googleapis.com/builddeps/de69a09dc70417580aabf20a28619bb3ef60d038470c7cf8442fafcf627c21cb",
    ],
)

http_archive(
    name = "io_bazel_rules_docker",
    sha256 = "95d39fd84ff4474babaf190450ee034d958202043e366b9fc38f438c9e6c3334",
    strip_prefix = "rules_docker-0.16.0",
    urls = [
        "https://github.com/bazelbuild/rules_docker/releases/download/v0.16.0/rules_docker-v0.16.0.tar.gz",
        "https://storage.googleapis.com/builddeps/95d39fd84ff4474babaf190450ee034d958202043e366b9fc38f438c9e6c3334",
    ],
)

http_archive(
    name = "com_github_ash2k_bazel_tools",
    sha256 = "46fdbc00930c8dc9d84690b5bd94db6b4683b061199967d2cda1cfbda8f02c49",
    strip_prefix = "bazel-tools-19b174803c0db1a01e77f10fa2079c35f54eed6e",
    urls = [
        "https://github.com/ash2k/bazel-tools/archive/19b174803c0db1a01e77f10fa2079c35f54eed6e.zip",
        "https://storage.googleapis.com/builddeps/46fdbc00930c8dc9d84690b5bd94db6b4683b061199967d2cda1cfbda8f02c49",
    ],
)

# Disk images
http_file(
    name = "alpine_image",
    sha256 = "a90150589e493d5b7e87297056b6e124d8af1b91fa2eb92bab61a839839e287b",
    urls = [
        "https://dl-cdn.alpinelinux.org/alpine/v3.16/releases/x86_64/alpine-virt-3.16.3-x86_64.iso",
        "https://storage.googleapis.com/builddeps/a90150589e493d5b7e87297056b6e124d8af1b91fa2eb92bab61a839839e287b",
    ],
)

http_file(
    name = "alpine_image_aarch64",
    sha256 = "f3510fa675a6480a5f86b3325e97ca764368a8138d95fc4ba2efaebb41f8e325",
    urls = [
        "https://dl-cdn.alpinelinux.org/alpine/v3.16/releases/aarch64/alpine-virt-3.16.3-aarch64.iso",
        "https://storage.googleapis.com/builddeps/f3510fa675a6480a5f86b3325e97ca764368a8138d95fc4ba2efaebb41f8e325",
    ],
)

http_file(
    name = "cirros_image",
    sha256 = "932fcae93574e242dc3d772d5235061747dfe537668443a1f0567d893614b464",
    urls = [
        "https://download.cirros-cloud.net/0.5.2/cirros-0.5.2-x86_64-disk.img",
        "https://storage.googleapis.com/builddeps/932fcae93574e242dc3d772d5235061747dfe537668443a1f0567d893614b464",
    ],
)

http_file(
    name = "cirros_image_aarch64",
    sha256 = "889c1117647b3b16cfc47957931c6573bf8e755fc9098fdcad13727b6c9f2629",
    urls = [
        "https://download.cirros-cloud.net/0.5.2/cirros-0.5.2-aarch64-disk.img",
        "https://storage.googleapis.com/builddeps/889c1117647b3b16cfc47957931c6573bf8e755fc9098fdcad13727b6c9f2629",
    ],
)

http_file(
    name = "virtio_win_image",
    sha256 = "b8a4bc66835c43091a85d35a10b59bd8b1b62b55ea9f02ec754f68bd32e82c0e",
    urls = [
        "https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/archive-virtio/virtio-win-0.1.217-1/virtio-win-0.1.217.iso",
        "https://storage.googleapis.com/builddeps/b8a4bc66835c43091a85d35a10b59bd8b1b62b55ea9f02ec754f68bd32e82c0e",
    ],
)

http_archive(
    name = "bazeldnf",
    sha256 = "bb4210a87f3f2006edb90fbade6df682979dc0330565f2550373f3eb012d928b",
    strip_prefix = "bazeldnf-0.5.5",
    urls = [
        "https://github.com/rmohr/bazeldnf/archive/v0.5.5.tar.gz",
        "https://storage.googleapis.com/builddeps/bb4210a87f3f2006edb90fbade6df682979dc0330565f2550373f3eb012d928b",
    ],
)

load(
    "@io_bazel_rules_go//go:deps.bzl",
    "go_register_toolchains",
    "go_rules_dependencies",
)
load("@bazeldnf//:deps.bzl", "bazeldnf_dependencies", "rpm")

go_rules_dependencies()

go_register_toolchains(
    go_version = "1.19.2",
    nogo = "@//:nogo_vet",
)

load("@com_github_ash2k_bazel_tools//goimports:deps.bzl", "goimports_dependencies")

goimports_dependencies()

load(
    "@bazel_gazelle//:deps.bzl",
    "gazelle_dependencies",
    "go_repository",
)

gazelle_dependencies()

load("@com_github_bazelbuild_buildtools//buildifier:deps.bzl", "buildifier_dependencies")

buildifier_dependencies()

bazeldnf_dependencies()

load(
    "@bazel_tools//tools/build_defs/repo:git.bzl",
    "git_repository",
)

# Dependency seems to be gone
# TODO fix on bazeldnf side
go_repository(
    name = "com_github_xi2_xz",
    commit = "48954b6210f8d154cb5f8484d3a3e1f83489309e",
    importpath = "github.com/xi2/xz",
)

# Winrmcli dependencies
go_repository(
    name = "com_github_masterzen_winrmcli",
    commit = "c85a68ee8b6e3ac95af2a5fd62d2f41c9e9c5f32",
    importpath = "github.com/masterzen/winrm-cli",
)

# Winrmcp deps
go_repository(
    name = "com_github_packer_community_winrmcp",
    commit = "c76d91c1e7db27b0868c5d09e292bb540616c9a2",
    importpath = "github.com/packer-community/winrmcp",
)

go_repository(
    name = "com_github_masterzen_winrm_cli",
    commit = "6f0c57dee4569c04f64c44c335752b415e5d73a7",
    importpath = "github.com/masterzen/winrm-cli",
)

go_repository(
    name = "com_github_masterzen_winrm",
    commit = "1d17eaf15943ca3554cdebb3b1b10aaa543a0b7e",
    importpath = "github.com/masterzen/winrm",
)

go_repository(
    name = "com_github_nu7hatch_gouuid",
    commit = "179d4d0c4d8d407a32af483c2354df1d2c91e6c3",
    importpath = "github.com/nu7hatch/gouuid",
)

go_repository(
    name = "com_github_dylanmei_iso8601",
    commit = "2075bf119b58e5576c6ed9f867b8f3d17f2e54d4",
    importpath = "github.com/dylanmei/iso8601",
)

go_repository(
    name = "com_github_gofrs_uuid",
    commit = "abfe1881e60ef34074c1b8d8c63b42565c356ed6",
    importpath = "github.com/gofrs/uuid",
)

go_repository(
    name = "com_github_christrenkamp_goxpath",
    commit = "c5096ec8773dd9f554971472081ddfbb0782334e",
    importpath = "github.com/ChrisTrenkamp/goxpath",
)

go_repository(
    name = "com_github_azure_go_ntlmssp",
    commit = "4a21cbd618b459155f8b8ee7f4491cd54f5efa77",
    importpath = "github.com/Azure/go-ntlmssp",
)

go_repository(
    name = "com_github_masterzen_simplexml",
    commit = "31eea30827864c9ab643aa5a0d5b2d4988ec8409",
    importpath = "github.com/masterzen/simplexml",
)

go_repository(
    name = "org_golang_x_crypto",
    commit = "4def268fd1a49955bfb3dda92fe3db4f924f2285",
    importpath = "golang.org/x/crypto",
)

# override rules_docker issue with this dependency
# rules_docker 0.16 uses 0.1.4, let's grab by commit
go_repository(
    name = "com_github_google_go_containerregistry",
    commit = "8a2841911ffee4f6892ca0083e89752fb46c48dd",  # v0.1.4
    importpath = "github.com/google/go-containerregistry",
)

# bazel docker rules
load(
    "@io_bazel_rules_docker//container:container.bzl",
    "container_image",
    "container_pull",
)
load(
    "@io_bazel_rules_docker//repositories:repositories.bzl",
    container_repositories = "repositories",
)

container_repositories()

load("@io_bazel_rules_docker//repositories:deps.bzl", container_deps = "deps")

container_deps()

# Pull go_image_base
container_pull(
    name = "go_image_base",
    digest = "sha256:839543093a9b27ac281cb9ae15f0272a410001b66720a4884068d74dfcaa7125",
    registry = "gcr.io",
    repository = "distroless/base",
)

container_pull(
    name = "go_image_base_aarch64",
    digest = "sha256:f62c7dfb39450d8345478f9fbc3aeaeab7ad93672dec31e95828dacf838099fa",
    registry = "gcr.io",
    repository = "distroless/base",
)

# Pull nfs-server image
# WARNING: please update any automated process to push this image to quay.io
# instead of index.docker.io
# TODO build nfs-server for multi-arch
container_pull(
    name = "nfs-server",
    digest = "sha256:8c1fa882dddb2885c4152e9ce632c466f4b8dce29339455e9b6bfe71f0a3d3ef",
    registry = "quay.io",
    repository = "kubevirtci/nfs-ganesha",  # see https://github.com/slintes/docker-nfs-ganesha
)

container_pull(
    name = "nfs-server_aarch64",
    digest = "sha256:8c1fa882dddb2885c4152e9ce632c466f4b8dce29339455e9b6bfe71f0a3d3ef",
    registry = "quay.io",
    repository = "kubevirtci/nfs-ganesha",  # see https://github.com/slintes/docker-nfs-ganesha
)

# Pull fedora container-disk preconfigured with ci tooling
# like stress and qemu guest agent pre-configured
# TODO build fedora_with_test_tooling for multi-arch
container_pull(
    name = "fedora_with_test_tooling",
    digest = "sha256:23dfbf35feb0ebfd2bcf85fe94c94f5ad50bca8762001ee0230f8381f79f52ef",
    registry = "quay.io",
    repository = "kubevirtci/fedora-with-test-tooling",
)

container_pull(
    name = "alpine_with_test_tooling",
    digest = "sha256:abd71660edffc355520239e8910debfa7491516ee35240f23bba378d9095410c",
    registry = "quay.io",
    repository = "kubevirtci/alpine-with-test-tooling-container-disk",
    tag = "2211021552-8cca8c0",
)

container_pull(
    name = "fedora_with_test_tooling_aarch64",
    digest = "sha256:9b1371260c05086a24ac9effdbedca9759c885ea8db93de7f0339df3bcd5a5c3",
    registry = "quay.io",
    repository = "kubevirtci/fedora-with-test-tooling",
)

container_pull(
    name = "alpine-ext-kernel-boot-demo-container-base",
    digest = "sha256:a2ddb2f568bf3814e594a14bc793d5a655a61d5983f3561d60d02afa7bbc56b4",
    registry = "quay.io",
    repository = "kubevirt/alpine-ext-kernel-boot-demo",
)

# TODO build fedora_realtime for multi-arch
container_pull(
    name = "fedora_realtime",
    digest = "sha256:437f4e02986daf0058239f4a282d32304dcac629d5d1b4c75a74025f1ce22811",
    registry = "quay.io",
    repository = "kubevirt/fedora-realtime-container-disk",
)

load(
    "@io_bazel_rules_docker//go:image.bzl",
    _go_image_repos = "repositories",
)

_go_image_repos()

http_archive(
    name = "io_bazel_rules_container_rpm",
    sha256 = "151261f1b81649de6e36f027c945722bff31176f1340682679cade2839e4b1e1",
    strip_prefix = "rules_container_rpm-0.0.5",
    urls = [
        "https://github.com/rmohr/rules_container_rpm/archive/v0.0.5.tar.gz",
        "https://storage.googleapis.com/builddeps/151261f1b81649de6e36f027c945722bff31176f1340682679cade2839e4b1e1",
    ],
)

http_archive(
    name = "libguestfs-appliance",
    sha256 = "124d6325a799e958843be4818ef2c32661755be1c56e519665779948861b04f6",
    urls = [
        "https://storage.googleapis.com/kubevirt-prow/devel/release/kubevirt/libguestfs-appliance/libguestfs-appliance-1.48.4-qcow2-linux-5.14.0-183-centos9.tar.xz",
    ],
)

# Get container-disk-v1alpha RPM's
http_file(
    name = "qemu-img",
    sha256 = "669250ad47aad5939cf4d1b88036fd95a94845d8e0bbdb05e933f3d2fe262fea",
    urls = ["https://storage.googleapis.com/builddeps/669250ad47aad5939cf4d1b88036fd95a94845d8e0bbdb05e933f3d2fe262fea"],
)

# some repos which are not part of go_rules anymore
go_repository(
    name = "com_github_golang_glog",
    importpath = "github.com/golang/glog",
    sum = "h1:VKtxabqXZkF25pY9ekfRL6a582T4P37/31XEstQ5p58=",
    version = "v0.0.0-20160126235308-23def4e6c14b",
)

go_repository(
    name = "org_golang_google_grpc",
    importpath = "google.golang.org/grpc",
    sum = "h1:M5a8xTlYTxwMn5ZFkwhRabsygDY5G8TYLyQDBxJNAxE=",
    version = "v1.30.0",
)

go_repository(
    name = "org_golang_x_net",
    importpath = "golang.org/x/net",
    sum = "h1:oWX7TPOiFAMXLq8o0ikBYfCJVlRHBcsciT5bXOrH628=",
    version = "v0.0.0-20190311183353-d8887717615a",
)

go_repository(
    name = "org_golang_x_text",
    importpath = "golang.org/x/text",
    sum = "h1:g61tztE5qeGQ89tm6NTjjM9VPIm088od1l6aSorWRWg=",
    version = "v0.3.0",
)

register_toolchains("//:py_toolchain")

go_repository(
    name = "org_golang_x_mod",
    build_file_generation = "on",
    build_file_proto_mode = "disable",
    importpath = "golang.org/x/mod",
    sum = "h1:RM4zey1++hCTbCVQfnWeKs9/IEsaBLA8vTkd0WVtmH4=",
    version = "v0.3.0",
)

go_repository(
    name = "org_golang_x_xerrors",
    build_file_generation = "on",
    build_file_proto_mode = "disable",
    importpath = "golang.org/x/xerrors",
    sum = "h1:go1bK/D/BFZV2I8cIQd1NKEZ+0owSTG1fDTci4IqFcE=",
    version = "v0.0.0-20200804184101-5ec99f83aff1",
)

rpm(
    name = "acl-0__2.3.1-3.el9.aarch64",
    sha256 = "151d6542a39243b5f65698b31edfe2d9c59e2fd71a7dcaa237442fc5d1d9de1e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/acl-2.3.1-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/151d6542a39243b5f65698b31edfe2d9c59e2fd71a7dcaa237442fc5d1d9de1e",
    ],
)

rpm(
    name = "acl-0__2.3.1-3.el9.x86_64",
    sha256 = "986044c3837eddbc9231d7be5e5fc517e245296978b988a803bc9f9172fe84ea",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/acl-2.3.1-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/986044c3837eddbc9231d7be5e5fc517e245296978b988a803bc9f9172fe84ea",
    ],
)

rpm(
    name = "alternatives-0__1.20-2.el9.aarch64",
    sha256 = "4d9055232088f1ab181e4741358aa188749b8195f184817c04a61447606cdfb5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/alternatives-1.20-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4d9055232088f1ab181e4741358aa188749b8195f184817c04a61447606cdfb5",
    ],
)

rpm(
    name = "alternatives-0__1.20-2.el9.x86_64",
    sha256 = "1851d5f64ebaeac67c5c2d9e4adc1e73aa6433b44a167268a3510c3d056062db",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/alternatives-1.20-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/1851d5f64ebaeac67c5c2d9e4adc1e73aa6433b44a167268a3510c3d056062db",
    ],
)

rpm(
    name = "audit-libs-0__3.0.7-103.el9.aarch64",
    sha256 = "d76fb317d2c119de235f079463163dc5a6ed8df8073aa747463697cb667ca604",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/audit-libs-3.0.7-103.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/d76fb317d2c119de235f079463163dc5a6ed8df8073aa747463697cb667ca604",
    ],
)

rpm(
    name = "audit-libs-0__3.0.7-103.el9.x86_64",
    sha256 = "cdd16764f76df434a731a331577fb03a51f19d0a8249ae782506e5ac12dabb0a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/audit-libs-3.0.7-103.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/cdd16764f76df434a731a331577fb03a51f19d0a8249ae782506e5ac12dabb0a",
    ],
)

rpm(
    name = "augeas-libs-0__1.13.0-5.el9.x86_64",
    sha256 = "d169ce09a7637372981eb379e619a1824181ca7201a768cb14e208895db2a22e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/augeas-libs-1.13.0-5.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d169ce09a7637372981eb379e619a1824181ca7201a768cb14e208895db2a22e",
    ],
)

rpm(
    name = "basesystem-0__11-13.el9.aarch64",
    sha256 = "a7a687ef39dd28d01d34fab18ea7e3e87f649f6c202dded82260b7ea625b9973",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/basesystem-11-13.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/a7a687ef39dd28d01d34fab18ea7e3e87f649f6c202dded82260b7ea625b9973",
    ],
)

rpm(
    name = "basesystem-0__11-13.el9.x86_64",
    sha256 = "a7a687ef39dd28d01d34fab18ea7e3e87f649f6c202dded82260b7ea625b9973",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/basesystem-11-13.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/a7a687ef39dd28d01d34fab18ea7e3e87f649f6c202dded82260b7ea625b9973",
    ],
)

rpm(
    name = "bash-0__5.1.8-6.el9.aarch64",
    sha256 = "adbea9afe78b2f67de854fdf5440326dda5383763797eb9ac486969edeecaef0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/bash-5.1.8-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/adbea9afe78b2f67de854fdf5440326dda5383763797eb9ac486969edeecaef0",
    ],
)

rpm(
    name = "bash-0__5.1.8-6.el9.x86_64",
    sha256 = "09f700a94e187a74f6f4a5f750082732e193d41392a85f042bdeb0bcbabe0a1f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/bash-5.1.8-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/09f700a94e187a74f6f4a5f750082732e193d41392a85f042bdeb0bcbabe0a1f",
    ],
)

rpm(
    name = "binutils-0__2.35.2-39.el9.aarch64",
    sha256 = "162e36f650c9351cb25c1483d2c8a75cc02a1705e4d594c6e283358685463642",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/binutils-2.35.2-39.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/162e36f650c9351cb25c1483d2c8a75cc02a1705e4d594c6e283358685463642",
    ],
)

rpm(
    name = "binutils-0__2.35.2-39.el9.x86_64",
    sha256 = "c7af3473e4636f48417bf0bcf74be2cf1ba99442041bcdcb102a5eddc66d5ab2",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/binutils-2.35.2-39.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c7af3473e4636f48417bf0bcf74be2cf1ba99442041bcdcb102a5eddc66d5ab2",
    ],
)

rpm(
    name = "binutils-gold-0__2.35.2-39.el9.aarch64",
    sha256 = "e3baef4c1b7b975056fe7c212e39d9ad57d20fec94efe1704407bf579583f498",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/binutils-gold-2.35.2-39.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/e3baef4c1b7b975056fe7c212e39d9ad57d20fec94efe1704407bf579583f498",
    ],
)

rpm(
    name = "binutils-gold-0__2.35.2-39.el9.x86_64",
    sha256 = "b0fd883d3875de33b64b83956f4e82487e3ac27306b2fd17104b5bd9ede7efcb",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/binutils-gold-2.35.2-39.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b0fd883d3875de33b64b83956f4e82487e3ac27306b2fd17104b5bd9ede7efcb",
    ],
)

rpm(
    name = "bzip2-0__1.0.8-8.el9.aarch64",
    sha256 = "d89b742bc5327741c3ff26a7fb17a518552bbad74c0c299f147af57a0a208b93",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/bzip2-1.0.8-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/d89b742bc5327741c3ff26a7fb17a518552bbad74c0c299f147af57a0a208b93",
    ],
)

rpm(
    name = "bzip2-0__1.0.8-8.el9.x86_64",
    sha256 = "90aeb088fad0093b1ca531387d38e1c32ad64efd56f2306eacc0edbc4c37e205",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/bzip2-1.0.8-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/90aeb088fad0093b1ca531387d38e1c32ad64efd56f2306eacc0edbc4c37e205",
    ],
)

rpm(
    name = "bzip2-libs-0__1.0.8-8.el9.aarch64",
    sha256 = "6c20f6f13c274fa2487f95f1e3dddcee9b931ce222abebd2f1d9b3f7eb69fcde",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/bzip2-libs-1.0.8-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/6c20f6f13c274fa2487f95f1e3dddcee9b931ce222abebd2f1d9b3f7eb69fcde",
    ],
)

rpm(
    name = "bzip2-libs-0__1.0.8-8.el9.x86_64",
    sha256 = "fabd6b5c065c2b9d4a8d39a938ae577d801de2ddc73c8cdf6f7803db29c28d0a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/bzip2-libs-1.0.8-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fabd6b5c065c2b9d4a8d39a938ae577d801de2ddc73c8cdf6f7803db29c28d0a",
    ],
)

rpm(
    name = "ca-certificates-0__2022.2.54-90.2.el9.aarch64",
    sha256 = "24978e8dd3e054583da86036657ab16e93da97a0bafc148ec28d871d8c15257c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/ca-certificates-2022.2.54-90.2.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/24978e8dd3e054583da86036657ab16e93da97a0bafc148ec28d871d8c15257c",
    ],
)

rpm(
    name = "ca-certificates-0__2022.2.54-90.2.el9.x86_64",
    sha256 = "24978e8dd3e054583da86036657ab16e93da97a0bafc148ec28d871d8c15257c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/ca-certificates-2022.2.54-90.2.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/24978e8dd3e054583da86036657ab16e93da97a0bafc148ec28d871d8c15257c",
    ],
)

rpm(
    name = "capstone-0__4.0.2-10.el9.aarch64",
    sha256 = "fe07aa69a9e6b70d0324e702b825ad55f330225ecb2af504f7026917e0ff197e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/capstone-4.0.2-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/fe07aa69a9e6b70d0324e702b825ad55f330225ecb2af504f7026917e0ff197e",
    ],
)

rpm(
    name = "capstone-0__4.0.2-10.el9.x86_64",
    sha256 = "f6a9fdc6bcb5da1b2ce44ca7ed6289759c37add7adbb19916dd36d5bb4624a41",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/capstone-4.0.2-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/f6a9fdc6bcb5da1b2ce44ca7ed6289759c37add7adbb19916dd36d5bb4624a41",
    ],
)

rpm(
    name = "centos-gpg-keys-0__9.0-21.el9.aarch64",
    sha256 = "86bb90722a589e0bd01be53b53caedbc4d5482057ecdaf31e9cafb1360f0df02",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/centos-gpg-keys-9.0-21.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/86bb90722a589e0bd01be53b53caedbc4d5482057ecdaf31e9cafb1360f0df02",
    ],
)

rpm(
    name = "centos-gpg-keys-0__9.0-21.el9.x86_64",
    sha256 = "86bb90722a589e0bd01be53b53caedbc4d5482057ecdaf31e9cafb1360f0df02",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/centos-gpg-keys-9.0-21.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/86bb90722a589e0bd01be53b53caedbc4d5482057ecdaf31e9cafb1360f0df02",
    ],
)

rpm(
    name = "centos-stream-release-0__9.0-21.el9.aarch64",
    sha256 = "4a9d6f5fa5ef78226b12efd0496b5f03c84b43d2413dac346e40f6abf527edf8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/centos-stream-release-9.0-21.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/4a9d6f5fa5ef78226b12efd0496b5f03c84b43d2413dac346e40f6abf527edf8",
    ],
)

rpm(
    name = "centos-stream-release-0__9.0-21.el9.x86_64",
    sha256 = "4a9d6f5fa5ef78226b12efd0496b5f03c84b43d2413dac346e40f6abf527edf8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/centos-stream-release-9.0-21.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/4a9d6f5fa5ef78226b12efd0496b5f03c84b43d2413dac346e40f6abf527edf8",
    ],
)

rpm(
    name = "centos-stream-repos-0__9.0-21.el9.aarch64",
    sha256 = "2b23dc5dca2de4d836f7ca928ffd4a15584df97e8e13413ee1e7a4c6a8529436",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/centos-stream-repos-9.0-21.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/2b23dc5dca2de4d836f7ca928ffd4a15584df97e8e13413ee1e7a4c6a8529436",
    ],
)

rpm(
    name = "centos-stream-repos-0__9.0-21.el9.x86_64",
    sha256 = "2b23dc5dca2de4d836f7ca928ffd4a15584df97e8e13413ee1e7a4c6a8529436",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/centos-stream-repos-9.0-21.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/2b23dc5dca2de4d836f7ca928ffd4a15584df97e8e13413ee1e7a4c6a8529436",
    ],
)

rpm(
    name = "coreutils-0__8.32-34.el9.aarch64",
    sha256 = "6b5f4a59c7f69cab60829b3664d6b1de9405fb0f4076e77adf95fdbee017529c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/coreutils-8.32-34.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/6b5f4a59c7f69cab60829b3664d6b1de9405fb0f4076e77adf95fdbee017529c",
    ],
)

rpm(
    name = "coreutils-common-0__8.32-34.el9.aarch64",
    sha256 = "e0bd37390b06691bbc78e773ca005387c502354934549f0e7d628f384d99b2f0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/coreutils-common-8.32-34.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/e0bd37390b06691bbc78e773ca005387c502354934549f0e7d628f384d99b2f0",
    ],
)

rpm(
    name = "coreutils-single-0__8.32-34.el9.aarch64",
    sha256 = "9ab931a79d42f2cf38ef98283603792abbef8c99d7cc112e04c69d0a66fb074c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/coreutils-single-8.32-34.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/9ab931a79d42f2cf38ef98283603792abbef8c99d7cc112e04c69d0a66fb074c",
    ],
)

rpm(
    name = "coreutils-single-0__8.32-34.el9.x86_64",
    sha256 = "fd6001340bdba2e7b49b6dee004dc7e54e5b2393bdb0c9de9ca2e8801e39e671",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/coreutils-single-8.32-34.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fd6001340bdba2e7b49b6dee004dc7e54e5b2393bdb0c9de9ca2e8801e39e671",
    ],
)

rpm(
    name = "cpp-0__11.3.1-4.4.el9.aarch64",
    sha256 = "0b14b3753e56c6bd30272f39b1004f1f3d3996fb9c70330dbe27392f2c24af09",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/cpp-11.3.1-4.4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/0b14b3753e56c6bd30272f39b1004f1f3d3996fb9c70330dbe27392f2c24af09",
    ],
)

rpm(
    name = "cpp-0__11.3.1-4.4.el9.x86_64",
    sha256 = "05ea8772d16ae7f88d818c88c3edc347b79f37488f08cb928bae469b56c37879",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/cpp-11.3.1-4.4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/05ea8772d16ae7f88d818c88c3edc347b79f37488f08cb928bae469b56c37879",
    ],
)

rpm(
    name = "cracklib-0__2.9.6-27.el9.aarch64",
    sha256 = "d92900088b558cd3c96c63db24b048a0f3ea575a0f8bfe66c26df4acfcb2f811",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/cracklib-2.9.6-27.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/d92900088b558cd3c96c63db24b048a0f3ea575a0f8bfe66c26df4acfcb2f811",
    ],
)

rpm(
    name = "cracklib-0__2.9.6-27.el9.x86_64",
    sha256 = "be9deb2efd06b4b2c1c130acae94c687161d04830119e65a989d904ba9fd1864",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/cracklib-2.9.6-27.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/be9deb2efd06b4b2c1c130acae94c687161d04830119e65a989d904ba9fd1864",
    ],
)

rpm(
    name = "cracklib-dicts-0__2.9.6-27.el9.aarch64",
    sha256 = "bfd16ac0aebb165d43d3139448ab8eac66d4d67c9eac506c3f3bef799f1352c2",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/cracklib-dicts-2.9.6-27.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/bfd16ac0aebb165d43d3139448ab8eac66d4d67c9eac506c3f3bef799f1352c2",
    ],
)

rpm(
    name = "cracklib-dicts-0__2.9.6-27.el9.x86_64",
    sha256 = "01df2a72fcdf988132e82764ce1a22a5a9513fa253b54e17d23058bdb53c2d85",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/cracklib-dicts-2.9.6-27.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/01df2a72fcdf988132e82764ce1a22a5a9513fa253b54e17d23058bdb53c2d85",
    ],
)

rpm(
    name = "crypto-policies-0__20221215-1.git9a18988.el9.aarch64",
    sha256 = "9a132069f88a63b7b2c146ffc4c17ed80f8ff57b69eb5affdec9cd1306dcf6ad",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/crypto-policies-20221215-1.git9a18988.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/9a132069f88a63b7b2c146ffc4c17ed80f8ff57b69eb5affdec9cd1306dcf6ad",
    ],
)

rpm(
    name = "crypto-policies-0__20221215-1.git9a18988.el9.x86_64",
    sha256 = "9a132069f88a63b7b2c146ffc4c17ed80f8ff57b69eb5affdec9cd1306dcf6ad",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/crypto-policies-20221215-1.git9a18988.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/9a132069f88a63b7b2c146ffc4c17ed80f8ff57b69eb5affdec9cd1306dcf6ad",
    ],
)

rpm(
    name = "curl-minimal-0__7.76.1-23.el9.aarch64",
    sha256 = "f88c384deed8e8de5444937489dbd31ff1c1690eb6ff0da42cc7daa2b2c7b0d4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/curl-minimal-7.76.1-23.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/f88c384deed8e8de5444937489dbd31ff1c1690eb6ff0da42cc7daa2b2c7b0d4",
    ],
)

rpm(
    name = "curl-minimal-0__7.76.1-23.el9.x86_64",
    sha256 = "3d2ed0db2e85e18edd897ae63b463255536e597abc6ca4b8f189bf08c263ed65",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/curl-minimal-7.76.1-23.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/3d2ed0db2e85e18edd897ae63b463255536e597abc6ca4b8f189bf08c263ed65",
    ],
)

rpm(
    name = "cyrus-sasl-0__2.1.27-21.el9.aarch64",
    sha256 = "3ad176b2bb0f6b89e8b9951cd207415d40859f1f46e9d60b79a6516a7783ff7c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/cyrus-sasl-2.1.27-21.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/3ad176b2bb0f6b89e8b9951cd207415d40859f1f46e9d60b79a6516a7783ff7c",
    ],
)

rpm(
    name = "cyrus-sasl-0__2.1.27-21.el9.x86_64",
    sha256 = "b919e98a1da12adaf63056e4b3fe068541fdcaea5b891ac32c50f70074e7a682",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/cyrus-sasl-2.1.27-21.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b919e98a1da12adaf63056e4b3fe068541fdcaea5b891ac32c50f70074e7a682",
    ],
)

rpm(
    name = "cyrus-sasl-gssapi-0__2.1.27-21.el9.aarch64",
    sha256 = "12e292b4e05934f8fc8ecc557b2b57c2844335a559f720140bb7810ef249c043",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/cyrus-sasl-gssapi-2.1.27-21.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/12e292b4e05934f8fc8ecc557b2b57c2844335a559f720140bb7810ef249c043",
    ],
)

rpm(
    name = "cyrus-sasl-gssapi-0__2.1.27-21.el9.x86_64",
    sha256 = "c7cba5ec41adada2d95348705d91a5ef7b4bca2f82ca22440e881ad28d2d27d0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/cyrus-sasl-gssapi-2.1.27-21.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c7cba5ec41adada2d95348705d91a5ef7b4bca2f82ca22440e881ad28d2d27d0",
    ],
)

rpm(
    name = "cyrus-sasl-lib-0__2.1.27-21.el9.aarch64",
    sha256 = "898d7094964022ca527a6596550b8d46499b3274f8c6a1ee632a98961012d80c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/cyrus-sasl-lib-2.1.27-21.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/898d7094964022ca527a6596550b8d46499b3274f8c6a1ee632a98961012d80c",
    ],
)

rpm(
    name = "cyrus-sasl-lib-0__2.1.27-21.el9.x86_64",
    sha256 = "fd4292a29759f9531bbc876d1818e7a83ccac76907234002f598671d7b338469",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/cyrus-sasl-lib-2.1.27-21.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fd4292a29759f9531bbc876d1818e7a83ccac76907234002f598671d7b338469",
    ],
)

rpm(
    name = "daxctl-libs-0__71.1-8.el9.x86_64",
    sha256 = "95bbf4ffb69cebc022fe3a2b35b828978d47e5b016747197ed5be34a57712432",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/daxctl-libs-71.1-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/95bbf4ffb69cebc022fe3a2b35b828978d47e5b016747197ed5be34a57712432",
    ],
)

rpm(
    name = "dbus-1__1.12.20-7.el9.aarch64",
    sha256 = "66b72600006e0be1b68bee4fb8fa0290a71ffa50586369d37a00128b1d3c4835",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/dbus-1.12.20-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/66b72600006e0be1b68bee4fb8fa0290a71ffa50586369d37a00128b1d3c4835",
    ],
)

rpm(
    name = "dbus-1__1.12.20-7.el9.x86_64",
    sha256 = "a1111141d56f30e206be37269294af8de24da02e65024187f9b4d474656b573a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/dbus-1.12.20-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/a1111141d56f30e206be37269294af8de24da02e65024187f9b4d474656b573a",
    ],
)

rpm(
    name = "dbus-broker-0__28-7.el9.aarch64",
    sha256 = "28a7abe52040dcda6e5d941206ef6e5c47478fcc06a9f05c2ab7dacc2afa9f42",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/dbus-broker-28-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/28a7abe52040dcda6e5d941206ef6e5c47478fcc06a9f05c2ab7dacc2afa9f42",
    ],
)

rpm(
    name = "dbus-broker-0__28-7.el9.x86_64",
    sha256 = "dd65bddd728ed08dcdba5d06b5a5af9f958e5718e8cab938783241bd8f4d1131",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/dbus-broker-28-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/dd65bddd728ed08dcdba5d06b5a5af9f958e5718e8cab938783241bd8f4d1131",
    ],
)

rpm(
    name = "dbus-common-1__1.12.20-7.el9.aarch64",
    sha256 = "b70a359af020f34116139d96e7f138c10e1bb32a219836b88045ffaa7f4a36a5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/dbus-common-1.12.20-7.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/b70a359af020f34116139d96e7f138c10e1bb32a219836b88045ffaa7f4a36a5",
    ],
)

rpm(
    name = "dbus-common-1__1.12.20-7.el9.x86_64",
    sha256 = "b70a359af020f34116139d96e7f138c10e1bb32a219836b88045ffaa7f4a36a5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/dbus-common-1.12.20-7.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/b70a359af020f34116139d96e7f138c10e1bb32a219836b88045ffaa7f4a36a5",
    ],
)

rpm(
    name = "dbus-libs-1__1.12.20-7.el9.aarch64",
    sha256 = "85b69752c83faf4c060164ced13f23e20bb27efe246c6bffeab311a5d4131f5c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/dbus-libs-1.12.20-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/85b69752c83faf4c060164ced13f23e20bb27efe246c6bffeab311a5d4131f5c",
    ],
)

rpm(
    name = "dbus-libs-1__1.12.20-7.el9.x86_64",
    sha256 = "c3d0a716e7b8e248a6662abbe7b34c46df8255b006dde1c98d29e1d18b0599e9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/dbus-libs-1.12.20-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c3d0a716e7b8e248a6662abbe7b34c46df8255b006dde1c98d29e1d18b0599e9",
    ],
)

rpm(
    name = "device-mapper-9__1.02.187-7.el9.aarch64",
    sha256 = "c323def908ed792767d14222b575755b3c74d7cae406623830490b878415b3ae",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/device-mapper-1.02.187-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/c323def908ed792767d14222b575755b3c74d7cae406623830490b878415b3ae",
    ],
)

rpm(
    name = "device-mapper-9__1.02.187-7.el9.x86_64",
    sha256 = "7054ad97c6e5abc446514bde257b7bc5ad5045e20c1465b312acd1f6c3c71f15",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/device-mapper-1.02.187-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7054ad97c6e5abc446514bde257b7bc5ad5045e20c1465b312acd1f6c3c71f15",
    ],
)

rpm(
    name = "device-mapper-libs-9__1.02.187-7.el9.aarch64",
    sha256 = "0b61254de264cf568d7173bcc853b7d3abee12361534898073458373cc295124",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/device-mapper-libs-1.02.187-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/0b61254de264cf568d7173bcc853b7d3abee12361534898073458373cc295124",
    ],
)

rpm(
    name = "device-mapper-libs-9__1.02.187-7.el9.x86_64",
    sha256 = "d131bed33ca675b886cdc7251ebb6a4793b4529cd9f6091f433f917119052e9d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/device-mapper-libs-1.02.187-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d131bed33ca675b886cdc7251ebb6a4793b4529cd9f6091f433f917119052e9d",
    ],
)

rpm(
    name = "device-mapper-multipath-libs-0__0.8.7-21.el9.aarch64",
    sha256 = "e346ca573a3e452cd1dcc294ff91b31605f3fdd47a7795c1a871cb29b599d91f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/device-mapper-multipath-libs-0.8.7-21.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/e346ca573a3e452cd1dcc294ff91b31605f3fdd47a7795c1a871cb29b599d91f",
    ],
)

rpm(
    name = "device-mapper-multipath-libs-0__0.8.7-21.el9.x86_64",
    sha256 = "08f90be3a42c96f1101e5ebdbfe853ff8a991a912f96ad79eaf9ba98ec490fd2",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/device-mapper-multipath-libs-0.8.7-21.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/08f90be3a42c96f1101e5ebdbfe853ff8a991a912f96ad79eaf9ba98ec490fd2",
    ],
)

rpm(
    name = "diffutils-0__3.7-12.el9.aarch64",
    sha256 = "4fea2be2558981a55a569cc7b93f17afce86bba830ebce32a0aa320e4759293e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/diffutils-3.7-12.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4fea2be2558981a55a569cc7b93f17afce86bba830ebce32a0aa320e4759293e",
    ],
)

rpm(
    name = "diffutils-0__3.7-12.el9.x86_64",
    sha256 = "fdebefc46badf2e700e00582041a0e5f5183dd4fdc04badfe47c91f030cea0ce",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/diffutils-3.7-12.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fdebefc46badf2e700e00582041a0e5f5183dd4fdc04badfe47c91f030cea0ce",
    ],
)

rpm(
    name = "dmidecode-1__3.3-7.el9.x86_64",
    sha256 = "2afb32bf0c30908817d57d221dbded83917aa8a88d2586e98ce548bad4f86e3d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/dmidecode-3.3-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/2afb32bf0c30908817d57d221dbded83917aa8a88d2586e98ce548bad4f86e3d",
    ],
)

rpm(
    name = "e2fsprogs-0__1.46.5-3.el9.aarch64",
    sha256 = "e2eea5a568a705df9ad4afa5b15bdaa1c7e8febef9ce0f51ea394f0145efb224",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/e2fsprogs-1.46.5-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/e2eea5a568a705df9ad4afa5b15bdaa1c7e8febef9ce0f51ea394f0145efb224",
    ],
)

rpm(
    name = "e2fsprogs-0__1.46.5-3.el9.x86_64",
    sha256 = "7fbb88e8ad5b578e157f383da089c9af4d5361dec8d23495b00f7f1102d6e4de",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/e2fsprogs-1.46.5-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7fbb88e8ad5b578e157f383da089c9af4d5361dec8d23495b00f7f1102d6e4de",
    ],
)

rpm(
    name = "e2fsprogs-libs-0__1.46.5-3.el9.aarch64",
    sha256 = "efc31e2b3a79208457bafe9fc61f6bee935dd021216cfe18567936b95487fdd0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/e2fsprogs-libs-1.46.5-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/efc31e2b3a79208457bafe9fc61f6bee935dd021216cfe18567936b95487fdd0",
    ],
)

rpm(
    name = "e2fsprogs-libs-0__1.46.5-3.el9.x86_64",
    sha256 = "0626ca08ef0d4ddafbb7679eb3915c61f0496038f92263529715681952854d20",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/e2fsprogs-libs-1.46.5-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/0626ca08ef0d4ddafbb7679eb3915c61f0496038f92263529715681952854d20",
    ],
)

rpm(
    name = "edk2-aarch64-0__20221207gitfff6d81270b5-9.el9.aarch64",
    sha256 = "59230c99a301b8c01c632db4bfd340881c6dc3ee7da5e5377529c2b3a776f93b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/edk2-aarch64-20221207gitfff6d81270b5-9.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/59230c99a301b8c01c632db4bfd340881c6dc3ee7da5e5377529c2b3a776f93b",
    ],
)

rpm(
    name = "edk2-ovmf-0__20221207gitfff6d81270b5-9.el9.x86_64",
    sha256 = "4d5ec39970608f33692f9f3d92db7f7bc136dad2c861213e9da170bc68c42064",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/edk2-ovmf-20221207gitfff6d81270b5-9.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/4d5ec39970608f33692f9f3d92db7f7bc136dad2c861213e9da170bc68c42064",
    ],
)

rpm(
    name = "elfutils-debuginfod-client-0__0.188-3.el9.aarch64",
    sha256 = "e60596263746c54f3f0cc7628ff69783debdf8d5f6f892e3e565f3b7762e543f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/elfutils-debuginfod-client-0.188-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/e60596263746c54f3f0cc7628ff69783debdf8d5f6f892e3e565f3b7762e543f",
    ],
)

rpm(
    name = "elfutils-debuginfod-client-0__0.188-3.el9.x86_64",
    sha256 = "d94b50eb8b80606cc1a8bc9e2037b466936bb1d9d5ac43e24b1337c433025805",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/elfutils-debuginfod-client-0.188-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d94b50eb8b80606cc1a8bc9e2037b466936bb1d9d5ac43e24b1337c433025805",
    ],
)

rpm(
    name = "elfutils-default-yama-scope-0__0.188-3.el9.aarch64",
    sha256 = "f1539e9f6ab6f0b94d683e0452ce7b6bc56513b7c6fd6f4116859c8cdb0d6005",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/elfutils-default-yama-scope-0.188-3.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/f1539e9f6ab6f0b94d683e0452ce7b6bc56513b7c6fd6f4116859c8cdb0d6005",
    ],
)

rpm(
    name = "elfutils-default-yama-scope-0__0.188-3.el9.x86_64",
    sha256 = "f1539e9f6ab6f0b94d683e0452ce7b6bc56513b7c6fd6f4116859c8cdb0d6005",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/elfutils-default-yama-scope-0.188-3.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/f1539e9f6ab6f0b94d683e0452ce7b6bc56513b7c6fd6f4116859c8cdb0d6005",
    ],
)

rpm(
    name = "elfutils-libelf-0__0.188-3.el9.aarch64",
    sha256 = "acb0a5c7ffb9cb083781bdfcbfa95c9ba040173e8366129540e7bffc9d9fe2f1",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/elfutils-libelf-0.188-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/acb0a5c7ffb9cb083781bdfcbfa95c9ba040173e8366129540e7bffc9d9fe2f1",
    ],
)

rpm(
    name = "elfutils-libelf-0__0.188-3.el9.x86_64",
    sha256 = "0991cf08a00a872558c419f9c0fb8011d34c205c573e12d1afd388055a051530",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/elfutils-libelf-0.188-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/0991cf08a00a872558c419f9c0fb8011d34c205c573e12d1afd388055a051530",
    ],
)

rpm(
    name = "elfutils-libs-0__0.188-3.el9.aarch64",
    sha256 = "676013ae7e462af8b5c2e030b64e84c0a4280abfc0e163c85aa688875f1fc8cb",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/elfutils-libs-0.188-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/676013ae7e462af8b5c2e030b64e84c0a4280abfc0e163c85aa688875f1fc8cb",
    ],
)

rpm(
    name = "elfutils-libs-0__0.188-3.el9.x86_64",
    sha256 = "019d049d65b9a559dec623264f2d2f35977cf6899a98ad0f339ed9dd40dfea1b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/elfutils-libs-0.188-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/019d049d65b9a559dec623264f2d2f35977cf6899a98ad0f339ed9dd40dfea1b",
    ],
)

rpm(
    name = "ethtool-2__6.2-1.el9.aarch64",
    sha256 = "9f086c7b6796d5749f5f93f727cbe380c9d04f54c968b5555db2763bace23e6a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/ethtool-6.2-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/9f086c7b6796d5749f5f93f727cbe380c9d04f54c968b5555db2763bace23e6a",
    ],
)

rpm(
    name = "ethtool-2__6.2-1.el9.x86_64",
    sha256 = "bc4b58cbda4ce3eb8795aa35db56c6e7d52a53f48b3c197d0ee83911f5d3eadc",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/ethtool-6.2-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/bc4b58cbda4ce3eb8795aa35db56c6e7d52a53f48b3c197d0ee83911f5d3eadc",
    ],
)

rpm(
    name = "expat-0__2.5.0-1.el9.aarch64",
    sha256 = "2163792c7a297e441d7c3c0cbef7a6da0695e44e0b16fbb796cd90ab91dfe0cb",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/expat-2.5.0-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/2163792c7a297e441d7c3c0cbef7a6da0695e44e0b16fbb796cd90ab91dfe0cb",
    ],
)

rpm(
    name = "expat-0__2.5.0-1.el9.x86_64",
    sha256 = "b5092845377c3505cd072a896c443abe5da21d3c6c6cb23d917db159905178a6",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/expat-2.5.0-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b5092845377c3505cd072a896c443abe5da21d3c6c6cb23d917db159905178a6",
    ],
)

rpm(
    name = "filesystem-0__3.16-2.el9.aarch64",
    sha256 = "0afb1f7582830fa9c8c58a6679ab3b4ccf8bbdf1c0c76908fea1429eec8b8a53",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/filesystem-3.16-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/0afb1f7582830fa9c8c58a6679ab3b4ccf8bbdf1c0c76908fea1429eec8b8a53",
    ],
)

rpm(
    name = "filesystem-0__3.16-2.el9.x86_64",
    sha256 = "b69a472751268a1b9acd566dc7aa486fc1d6c8cb6d23f36d6a6dfead62e71475",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/filesystem-3.16-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b69a472751268a1b9acd566dc7aa486fc1d6c8cb6d23f36d6a6dfead62e71475",
    ],
)

rpm(
    name = "findutils-1__4.8.0-5.el9.aarch64",
    sha256 = "3ae59472d5b58715c452f74cb865dbe4058d155ed30d3908a96c51ccccaf4e82",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/findutils-4.8.0-5.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/3ae59472d5b58715c452f74cb865dbe4058d155ed30d3908a96c51ccccaf4e82",
    ],
)

rpm(
    name = "findutils-1__4.8.0-5.el9.x86_64",
    sha256 = "552548e6d6f9623ccd9d31bb185bba3a66730da6e9d02296b417d501356c3848",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/findutils-4.8.0-5.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/552548e6d6f9623ccd9d31bb185bba3a66730da6e9d02296b417d501356c3848",
    ],
)

rpm(
    name = "fuse-0__2.9.9-15.el9.x86_64",
    sha256 = "f0f8b58029ffddf73c5147c67c8e5f90f60e0e315f195c25695ceb0e9fec9d4b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/fuse-2.9.9-15.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/f0f8b58029ffddf73c5147c67c8e5f90f60e0e315f195c25695ceb0e9fec9d4b",
    ],
)

rpm(
    name = "fuse-common-0__3.10.2-5.el9.x86_64",
    sha256 = "a156d82484b61b6323524631d80c8d184042e8819a6d86a1b9b3076f3b5f3612",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/fuse-common-3.10.2-5.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/a156d82484b61b6323524631d80c8d184042e8819a6d86a1b9b3076f3b5f3612",
    ],
)

rpm(
    name = "fuse-libs-0__2.9.9-15.el9.aarch64",
    sha256 = "d82ebf3bcfe85eae2b34c4dbd507d8a0b0ac05d4df4c9ee16fee7555f36c7873",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/fuse-libs-2.9.9-15.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/d82ebf3bcfe85eae2b34c4dbd507d8a0b0ac05d4df4c9ee16fee7555f36c7873",
    ],
)

rpm(
    name = "fuse-libs-0__2.9.9-15.el9.x86_64",
    sha256 = "610c601daea8fa587c3ee43f2af06c25c506caf4588bf214e04de7eb960b95fa",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/fuse-libs-2.9.9-15.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/610c601daea8fa587c3ee43f2af06c25c506caf4588bf214e04de7eb960b95fa",
    ],
)

rpm(
    name = "gawk-0__5.1.0-6.el9.aarch64",
    sha256 = "656d23c583b0705eaad75cffbe880f2ec39c7d5b7a756c6a8853c2977eec331b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/gawk-5.1.0-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/656d23c583b0705eaad75cffbe880f2ec39c7d5b7a756c6a8853c2977eec331b",
    ],
)

rpm(
    name = "gawk-0__5.1.0-6.el9.x86_64",
    sha256 = "6e6d77b76b1e89fe6f012cdc16111bea35eb4ceedac5040e5d81b5a066429af8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/gawk-5.1.0-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/6e6d77b76b1e89fe6f012cdc16111bea35eb4ceedac5040e5d81b5a066429af8",
    ],
)

rpm(
    name = "gcc-0__11.3.1-4.4.el9.aarch64",
    sha256 = "3f4988fa051f3422e81a9b06674b6a73fa58c585299f798ea94a46d2c528430b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/gcc-11.3.1-4.4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/3f4988fa051f3422e81a9b06674b6a73fa58c585299f798ea94a46d2c528430b",
    ],
)

rpm(
    name = "gcc-0__11.3.1-4.4.el9.x86_64",
    sha256 = "6c06695708cd1876bad881852444649d446b234b0113871bdd5fe3a921fd7c39",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/gcc-11.3.1-4.4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/6c06695708cd1876bad881852444649d446b234b0113871bdd5fe3a921fd7c39",
    ],
)

rpm(
    name = "gdbm-libs-1__1.19-4.el9.aarch64",
    sha256 = "4fc723b43287c971507ec7899a1517dcc91abab962707febc7fdd9c1d865ace8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/gdbm-libs-1.19-4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4fc723b43287c971507ec7899a1517dcc91abab962707febc7fdd9c1d865ace8",
    ],
)

rpm(
    name = "gdbm-libs-1__1.19-4.el9.x86_64",
    sha256 = "8cd5a78cab8783dd241c52c4fcda28fb111c443887dd6d0fe38385e8383c98b3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/gdbm-libs-1.19-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/8cd5a78cab8783dd241c52c4fcda28fb111c443887dd6d0fe38385e8383c98b3",
    ],
)

rpm(
    name = "gettext-0__0.21-7.el9.aarch64",
    sha256 = "ba6583dd3960106d255266c1428d7b1f2383e75e14101a4f46e61053237c2920",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/gettext-0.21-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/ba6583dd3960106d255266c1428d7b1f2383e75e14101a4f46e61053237c2920",
    ],
)

rpm(
    name = "gettext-0__0.21-7.el9.x86_64",
    sha256 = "386905ddacb2614d519ec5dbaf038d40dbc44307b0edaa0bd3e6a5baa405a7b8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/gettext-0.21-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/386905ddacb2614d519ec5dbaf038d40dbc44307b0edaa0bd3e6a5baa405a7b8",
    ],
)

rpm(
    name = "gettext-libs-0__0.21-7.el9.aarch64",
    sha256 = "3114d6de7dadd0dae0b520f776ef7da581fe39fde3880ec9dbedf58bafc6b1c9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/gettext-libs-0.21-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/3114d6de7dadd0dae0b520f776ef7da581fe39fde3880ec9dbedf58bafc6b1c9",
    ],
)

rpm(
    name = "gettext-libs-0__0.21-7.el9.x86_64",
    sha256 = "1388fca61334c67cac638edba2459b362cc401c8ff5ab8d7d5ca387b0ffc8786",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/gettext-libs-0.21-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/1388fca61334c67cac638edba2459b362cc401c8ff5ab8d7d5ca387b0ffc8786",
    ],
)

rpm(
    name = "glib2-0__2.68.4-6.el9.aarch64",
    sha256 = "97c854640b8b99936fa4f5af4d28f2e478a77c346f69ffc3d66a5743c9551e69",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/glib2-2.68.4-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/97c854640b8b99936fa4f5af4d28f2e478a77c346f69ffc3d66a5743c9551e69",
    ],
)

rpm(
    name = "glib2-0__2.68.4-6.el9.x86_64",
    sha256 = "e8f2fd55fa576c57811f260ff5416411d39013bfe4b74bc8db87b8fc49b82705",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/glib2-2.68.4-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/e8f2fd55fa576c57811f260ff5416411d39013bfe4b74bc8db87b8fc49b82705",
    ],
)

rpm(
    name = "glibc-0__2.34-63.el9.aarch64",
    sha256 = "4aa338c407a73180df223eb2c2b279de21593bddf861f0bf3821caf156e5e457",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/glibc-2.34-63.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4aa338c407a73180df223eb2c2b279de21593bddf861f0bf3821caf156e5e457",
    ],
)

rpm(
    name = "glibc-0__2.34-63.el9.x86_64",
    sha256 = "3ab863193527c85114c837bfb5fe861bb33dfad5d6eb9b2993c9b37352f14553",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/glibc-2.34-63.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/3ab863193527c85114c837bfb5fe861bb33dfad5d6eb9b2993c9b37352f14553",
    ],
)

rpm(
    name = "glibc-common-0__2.34-63.el9.aarch64",
    sha256 = "39445f6ae0d2b72a76ee522f6de93fefda20c27fa408626ca1bf5490a7eebbe0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/glibc-common-2.34-63.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/39445f6ae0d2b72a76ee522f6de93fefda20c27fa408626ca1bf5490a7eebbe0",
    ],
)

rpm(
    name = "glibc-common-0__2.34-63.el9.x86_64",
    sha256 = "214a14c6f5c5cb7090f384531578ecafbd415752811c7e752de074af840ed668",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/glibc-common-2.34-63.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/214a14c6f5c5cb7090f384531578ecafbd415752811c7e752de074af840ed668",
    ],
)

rpm(
    name = "glibc-devel-0__2.34-63.el9.aarch64",
    sha256 = "dd9c3931c25cd4b407648498fd53fe0af80ada6a447f71614c3227379c471fb8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/glibc-devel-2.34-63.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/dd9c3931c25cd4b407648498fd53fe0af80ada6a447f71614c3227379c471fb8",
    ],
)

rpm(
    name = "glibc-devel-0__2.34-63.el9.x86_64",
    sha256 = "6cb8e7177c8efd8470a57581ba962c4eec461544499d2e07443b545799609ff4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/glibc-devel-2.34-63.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/6cb8e7177c8efd8470a57581ba962c4eec461544499d2e07443b545799609ff4",
    ],
)

rpm(
    name = "glibc-headers-0__2.34-63.el9.x86_64",
    sha256 = "607a72afd9bd13ddef98125806ec96c772ffb0fcf0e87ed34ecb37db9227ccb8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/glibc-headers-2.34-63.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/607a72afd9bd13ddef98125806ec96c772ffb0fcf0e87ed34ecb37db9227ccb8",
    ],
)

rpm(
    name = "glibc-langpack-fa-0__2.34-63.el9.x86_64",
    sha256 = "1a8b9c2511965faa850de8132a777ef7df4559129f22db501db2a362259318be",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/glibc-langpack-fa-2.34-63.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/1a8b9c2511965faa850de8132a777ef7df4559129f22db501db2a362259318be",
    ],
)

rpm(
    name = "glibc-langpack-nan-0__2.34-63.el9.aarch64",
    sha256 = "b5b62796b55c46436700659e1a16c50fef89fe3d88e3190378d275a298ac10a7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/glibc-langpack-nan-2.34-63.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/b5b62796b55c46436700659e1a16c50fef89fe3d88e3190378d275a298ac10a7",
    ],
)

rpm(
    name = "glibc-minimal-langpack-0__2.34-63.el9.aarch64",
    sha256 = "b825afb36f8bda60bfb034311979596beac8bf449ee34c6ca9d7eff6381ba425",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/glibc-minimal-langpack-2.34-63.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/b825afb36f8bda60bfb034311979596beac8bf449ee34c6ca9d7eff6381ba425",
    ],
)

rpm(
    name = "glibc-minimal-langpack-0__2.34-63.el9.x86_64",
    sha256 = "54423dad25755c73becb8fd6bfa000f9fc66c34192169ea91a3e6b245bedf54b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/glibc-minimal-langpack-2.34-63.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/54423dad25755c73becb8fd6bfa000f9fc66c34192169ea91a3e6b245bedf54b",
    ],
)

rpm(
    name = "glibc-static-0__2.34-63.el9.aarch64",
    sha256 = "ee75f6b4eaf0f8f6f88a33ac1c2c2717da3a48e9f4e3b13203d98a6399e3b28a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/CRB/aarch64/os/Packages/glibc-static-2.34-63.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/ee75f6b4eaf0f8f6f88a33ac1c2c2717da3a48e9f4e3b13203d98a6399e3b28a",
    ],
)

rpm(
    name = "glibc-static-0__2.34-63.el9.x86_64",
    sha256 = "18067a4eaee505e47b0f47007d3edc45385738d3637c5f7a5a604dbf80c6b29f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/CRB/x86_64/os/Packages/glibc-static-2.34-63.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/18067a4eaee505e47b0f47007d3edc45385738d3637c5f7a5a604dbf80c6b29f",
    ],
)

rpm(
    name = "gmp-1__6.2.0-10.el9.aarch64",
    sha256 = "1fe837ca20f20f8291a32c0f4673ea2560f94d75d25ab5131f6ae271694a4b44",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/gmp-6.2.0-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/1fe837ca20f20f8291a32c0f4673ea2560f94d75d25ab5131f6ae271694a4b44",
    ],
)

rpm(
    name = "gmp-1__6.2.0-10.el9.x86_64",
    sha256 = "1a6ededc80029ef258288ddbf24bcce7c6228647841416950c88e3f14b7258a2",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/gmp-6.2.0-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/1a6ededc80029ef258288ddbf24bcce7c6228647841416950c88e3f14b7258a2",
    ],
)

rpm(
    name = "gnupg2-0__2.3.3-2.el9.x86_64",
    sha256 = "d537e48c6947c6086d1af21b81b2619931b0ff708606d7545e388bbea05dcf32",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/gnupg2-2.3.3-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d537e48c6947c6086d1af21b81b2619931b0ff708606d7545e388bbea05dcf32",
    ],
)

rpm(
    name = "gnutls-0__3.7.6-20.el9.aarch64",
    sha256 = "a33e650f5b63b10e045bd81cacbd9cb4ab3b5ff2da6ac8cfb6bf4567ecbf4df3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/gnutls-3.7.6-20.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/a33e650f5b63b10e045bd81cacbd9cb4ab3b5ff2da6ac8cfb6bf4567ecbf4df3",
    ],
)

rpm(
    name = "gnutls-0__3.7.6-20.el9.x86_64",
    sha256 = "fc597ef5acc91687cc379e9ce4c91c0639ccaf46e201d04f06a05c4795e7590c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/gnutls-3.7.6-20.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fc597ef5acc91687cc379e9ce4c91c0639ccaf46e201d04f06a05c4795e7590c",
    ],
)

rpm(
    name = "gnutls-dane-0__3.7.6-20.el9.aarch64",
    sha256 = "6f1da5a7c67dbfacb8a797dd0e5b310618d62fe6b94ddb1f8a5b53586d7c365e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/gnutls-dane-3.7.6-20.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/6f1da5a7c67dbfacb8a797dd0e5b310618d62fe6b94ddb1f8a5b53586d7c365e",
    ],
)

rpm(
    name = "gnutls-dane-0__3.7.6-20.el9.x86_64",
    sha256 = "d27aab8b03f192d5bdd9be8f2a8453e30a96cbd32a855b1cfa901743ad54b4df",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/gnutls-dane-3.7.6-20.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d27aab8b03f192d5bdd9be8f2a8453e30a96cbd32a855b1cfa901743ad54b4df",
    ],
)

rpm(
    name = "gnutls-utils-0__3.7.6-20.el9.aarch64",
    sha256 = "4d167906bbb94190616ce26128a45a58013762ec8165c7ff16c2db3c72da290a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/gnutls-utils-3.7.6-20.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4d167906bbb94190616ce26128a45a58013762ec8165c7ff16c2db3c72da290a",
    ],
)

rpm(
    name = "gnutls-utils-0__3.7.6-20.el9.x86_64",
    sha256 = "0cf90183de61a0a978bb516b98fbd53f0e45607a90181fbf1723c6ff2e2a22d7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/gnutls-utils-3.7.6-20.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/0cf90183de61a0a978bb516b98fbd53f0e45607a90181fbf1723c6ff2e2a22d7",
    ],
)

rpm(
    name = "gobject-introspection-0__1.68.0-11.el9.aarch64",
    sha256 = "bcb5e3ab1d0ee579a11ec1449585196c0d13b552f73bbea3e2ada642b5313fbd",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/gobject-introspection-1.68.0-11.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/bcb5e3ab1d0ee579a11ec1449585196c0d13b552f73bbea3e2ada642b5313fbd",
    ],
)

rpm(
    name = "gobject-introspection-0__1.68.0-11.el9.x86_64",
    sha256 = "d75cc220f9b5978bb1755cf5e4de30244ff8e7ad7f98dfbdfe897f41442e4587",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/gobject-introspection-1.68.0-11.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d75cc220f9b5978bb1755cf5e4de30244ff8e7ad7f98dfbdfe897f41442e4587",
    ],
)

rpm(
    name = "grep-0__3.6-5.el9.aarch64",
    sha256 = "33bdf571a62cb8b7d659617e9278e46043aa936f8e963202750d19463a805f60",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/grep-3.6-5.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/33bdf571a62cb8b7d659617e9278e46043aa936f8e963202750d19463a805f60",
    ],
)

rpm(
    name = "grep-0__3.6-5.el9.x86_64",
    sha256 = "10a41b66b1fbd6eb055178e22c37199e5b49b4852e77c806f7af7211044a4a55",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/grep-3.6-5.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/10a41b66b1fbd6eb055178e22c37199e5b49b4852e77c806f7af7211044a4a55",
    ],
)

rpm(
    name = "gssproxy-0__0.8.4-4.el9.x86_64",
    sha256 = "bc7b37a4bc3342ca7884f0166b4124d68b51b75ead9f8e996ddbd0125ab571d5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/gssproxy-0.8.4-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/bc7b37a4bc3342ca7884f0166b4124d68b51b75ead9f8e996ddbd0125ab571d5",
    ],
)

rpm(
    name = "guestfs-tools-0__1.48.2-8.el9.x86_64",
    sha256 = "b423ad40665e919d487278ae7d5c88734c724c3dabd14b3201bb44b6e11554b1",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/guestfs-tools-1.48.2-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b423ad40665e919d487278ae7d5c88734c724c3dabd14b3201bb44b6e11554b1",
    ],
)

rpm(
    name = "gzip-0__1.12-1.el9.aarch64",
    sha256 = "5a39a441dad01ccc8af601f1cca5bed46ac231fbdbe39ea3202bd54cf9390d81",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/gzip-1.12-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/5a39a441dad01ccc8af601f1cca5bed46ac231fbdbe39ea3202bd54cf9390d81",
    ],
)

rpm(
    name = "gzip-0__1.12-1.el9.x86_64",
    sha256 = "e8d7783c666a58ab870246b04eb0ea22965123fe284697d2c0e1e6dbf10ea861",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/gzip-1.12-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/e8d7783c666a58ab870246b04eb0ea22965123fe284697d2c0e1e6dbf10ea861",
    ],
)

rpm(
    name = "hexedit-0__1.6-1.el9.x86_64",
    sha256 = "8c0781f044f9e45329cfc0f4c7d7acd65c9f779b34816c205279f977919e856f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/hexedit-1.6-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/8c0781f044f9e45329cfc0f4c7d7acd65c9f779b34816c205279f977919e856f",
    ],
)

rpm(
    name = "hivex-libs-0__1.3.21-3.el9.x86_64",
    sha256 = "3b0b567737f8a78e9264a07f935b25098f505d2b46653dba944919da85020ef7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/hivex-libs-1.3.21-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/3b0b567737f8a78e9264a07f935b25098f505d2b46653dba944919da85020ef7",
    ],
)

rpm(
    name = "iproute-0__6.1.0-1.el9.aarch64",
    sha256 = "3659a83bd8c40d1b281dc37534c25b0fc625ec32a3c52adc881f454e905c597a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/iproute-6.1.0-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/3659a83bd8c40d1b281dc37534c25b0fc625ec32a3c52adc881f454e905c597a",
    ],
)

rpm(
    name = "iproute-0__6.1.0-1.el9.x86_64",
    sha256 = "617291727b88271ffd18b98a4256ade0a546c5a5ca48ffe57538aca76f3000e8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/iproute-6.1.0-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/617291727b88271ffd18b98a4256ade0a546c5a5ca48ffe57538aca76f3000e8",
    ],
)

rpm(
    name = "iproute-tc-0__6.1.0-1.el9.aarch64",
    sha256 = "cb080b8adcaceda44ea6928b613d54f4dae14b089a756fea544486b6a63711e3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/iproute-tc-6.1.0-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/cb080b8adcaceda44ea6928b613d54f4dae14b089a756fea544486b6a63711e3",
    ],
)

rpm(
    name = "iproute-tc-0__6.1.0-1.el9.x86_64",
    sha256 = "c6052afc8aeb4aecf8c5dc24943878107d2fedb15ea17e4de34d6f6d205d8d88",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/iproute-tc-6.1.0-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c6052afc8aeb4aecf8c5dc24943878107d2fedb15ea17e4de34d6f6d205d8d88",
    ],
)

rpm(
    name = "iptables-libs-0__1.8.8-6.el9.aarch64",
    sha256 = "a0572f3b2eddcc18370801fd86bf6e5ed729702b63fadfc032c9855661090639",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/iptables-libs-1.8.8-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/a0572f3b2eddcc18370801fd86bf6e5ed729702b63fadfc032c9855661090639",
    ],
)

rpm(
    name = "iptables-libs-0__1.8.8-6.el9.x86_64",
    sha256 = "c1e4ebce15d824604e777993f46b94706239044c81bc5240e9541b1ae93485a5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/iptables-libs-1.8.8-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c1e4ebce15d824604e777993f46b94706239044c81bc5240e9541b1ae93485a5",
    ],
)

rpm(
    name = "iputils-0__20210202-8.el9.aarch64",
    sha256 = "4aac0e04d11130bf2fe1b2e050397de8e0e655065eddcf4e8b62e927479a4917",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/iputils-20210202-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4aac0e04d11130bf2fe1b2e050397de8e0e655065eddcf4e8b62e927479a4917",
    ],
)

rpm(
    name = "iputils-0__20210202-8.el9.x86_64",
    sha256 = "b15d6864679db8f723051552a289fe284829bde26bb8eacbe124e3a7f983f2ff",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/iputils-20210202-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b15d6864679db8f723051552a289fe284829bde26bb8eacbe124e3a7f983f2ff",
    ],
)

rpm(
    name = "ipxe-roms-qemu-0__20200823-9.git4bd064de.el9.x86_64",
    sha256 = "fa304f6cffa4a84a8aae1e0d2dd10606ffb51b88d9568b7da92ffd63acb14851",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/ipxe-roms-qemu-20200823-9.git4bd064de.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/fa304f6cffa4a84a8aae1e0d2dd10606ffb51b88d9568b7da92ffd63acb14851",
    ],
)

rpm(
    name = "jansson-0__2.14-1.el9.aarch64",
    sha256 = "23a8033dae909a6b87db199e04ecbc9798820b1b939e12d51733fed4554b9279",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/jansson-2.14-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/23a8033dae909a6b87db199e04ecbc9798820b1b939e12d51733fed4554b9279",
    ],
)

rpm(
    name = "jansson-0__2.14-1.el9.x86_64",
    sha256 = "c3fb9f8020f978f9b392709996e62e4ddb6cb19074635af3338487195b688f66",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/jansson-2.14-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c3fb9f8020f978f9b392709996e62e4ddb6cb19074635af3338487195b688f66",
    ],
)

rpm(
    name = "json-glib-0__1.6.6-1.el9.aarch64",
    sha256 = "04a7348a546a972f275a4de34373ad7a937a5a93f4c868dffa47daa31a226243",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/json-glib-1.6.6-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/04a7348a546a972f275a4de34373ad7a937a5a93f4c868dffa47daa31a226243",
    ],
)

rpm(
    name = "json-glib-0__1.6.6-1.el9.x86_64",
    sha256 = "d850cb45d31fe84cb50cb1fa26eb5418633aae1f0dcab8b7ebadd3bd3e340956",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/json-glib-1.6.6-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d850cb45d31fe84cb50cb1fa26eb5418633aae1f0dcab8b7ebadd3bd3e340956",
    ],
)

rpm(
    name = "kernel-headers-0__5.14.0-295.el9.aarch64",
    sha256 = "a9315f4da91a0afcc81a61083929836bdbcf9def28d12d2563478fd871ec5397",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/kernel-headers-5.14.0-295.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/a9315f4da91a0afcc81a61083929836bdbcf9def28d12d2563478fd871ec5397",
    ],
)

rpm(
    name = "kernel-headers-0__5.14.0-295.el9.x86_64",
    sha256 = "1188c0c3b4f4b7b9d3da06bc2bd9d53a3e20ddd83ece7474cb120da45d2f689c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/kernel-headers-5.14.0-295.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/1188c0c3b4f4b7b9d3da06bc2bd9d53a3e20ddd83ece7474cb120da45d2f689c",
    ],
)

rpm(
    name = "keyutils-0__1.6.3-1.el9.x86_64",
    sha256 = "bc9b6262006e7722b7936e3d1e5079d7281f96e161bcd0aa93328564a32984bb",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/keyutils-1.6.3-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/bc9b6262006e7722b7936e3d1e5079d7281f96e161bcd0aa93328564a32984bb",
    ],
)

rpm(
    name = "keyutils-libs-0__1.6.3-1.el9.aarch64",
    sha256 = "5d97ee3ed28533eb2ea01a6be97696fbbbc72f8178dcf7f1acf30e674a298a6e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/keyutils-libs-1.6.3-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/5d97ee3ed28533eb2ea01a6be97696fbbbc72f8178dcf7f1acf30e674a298a6e",
    ],
)

rpm(
    name = "keyutils-libs-0__1.6.3-1.el9.x86_64",
    sha256 = "aef982501694486a27411c68698886d76ec70c5cd10bfe619501e7e4c36f50a9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/keyutils-libs-1.6.3-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/aef982501694486a27411c68698886d76ec70c5cd10bfe619501e7e4c36f50a9",
    ],
)

rpm(
    name = "kmod-0__28-8.el9.aarch64",
    sha256 = "63d0ddb22a8e1540abf8018f336d2b5d95f39d25156315fa3352a5664c8046b0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/kmod-28-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/63d0ddb22a8e1540abf8018f336d2b5d95f39d25156315fa3352a5664c8046b0",
    ],
)

rpm(
    name = "kmod-0__28-8.el9.x86_64",
    sha256 = "c1fbcd43dbfc74f46619075f631ba468635a4e4aa99e84de388d0a4df39b0666",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/kmod-28-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c1fbcd43dbfc74f46619075f631ba468635a4e4aa99e84de388d0a4df39b0666",
    ],
)

rpm(
    name = "kmod-libs-0__28-8.el9.aarch64",
    sha256 = "45b810af8604d62566489e19b4eb286cbbde2cb4d3b65fea9f5a43471dc9d072",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/kmod-libs-28-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/45b810af8604d62566489e19b4eb286cbbde2cb4d3b65fea9f5a43471dc9d072",
    ],
)

rpm(
    name = "kmod-libs-0__28-8.el9.x86_64",
    sha256 = "64a63b3b22add198d0b87c59346609d560bc44c046ddc3b8a3ab9f43e30b81b1",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/kmod-libs-28-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/64a63b3b22add198d0b87c59346609d560bc44c046ddc3b8a3ab9f43e30b81b1",
    ],
)

rpm(
    name = "krb5-libs-0__1.20.1-8.el9.aarch64",
    sha256 = "d61a26b21aa401d07c411341be1038fff0b10132209cdc8481534f2a5e31f01d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/krb5-libs-1.20.1-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/d61a26b21aa401d07c411341be1038fff0b10132209cdc8481534f2a5e31f01d",
    ],
)

rpm(
    name = "krb5-libs-0__1.20.1-8.el9.x86_64",
    sha256 = "d3f350574b90454afdcb787e520bcaec76e176c287869d84fbe36ab4b91de323",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/krb5-libs-1.20.1-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d3f350574b90454afdcb787e520bcaec76e176c287869d84fbe36ab4b91de323",
    ],
)

rpm(
    name = "less-0__590-1.el9.x86_64",
    sha256 = "75ec2628be5ebe149a79b00f2160b9653297651d5ea291022e053719d2ff07f5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/less-590-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/75ec2628be5ebe149a79b00f2160b9653297651d5ea291022e053719d2ff07f5",
    ],
)

rpm(
    name = "libacl-0__2.3.1-3.el9.aarch64",
    sha256 = "4975593414dfa1e822cd108e988d18453c2ff036b03e4cdbf38db0afb45e0c92",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libacl-2.3.1-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4975593414dfa1e822cd108e988d18453c2ff036b03e4cdbf38db0afb45e0c92",
    ],
)

rpm(
    name = "libacl-0__2.3.1-3.el9.x86_64",
    sha256 = "fd829e9a03f6d321313002d6fcb37ee0434f548aa75fcd3ecdbdd891115de6a7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libacl-2.3.1-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fd829e9a03f6d321313002d6fcb37ee0434f548aa75fcd3ecdbdd891115de6a7",
    ],
)

rpm(
    name = "libaio-0__0.3.111-13.el9.aarch64",
    sha256 = "1730d732818fa2471b5cd461175ceda18e909410db8a32185d8db2aa7461130c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libaio-0.3.111-13.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/1730d732818fa2471b5cd461175ceda18e909410db8a32185d8db2aa7461130c",
    ],
)

rpm(
    name = "libaio-0__0.3.111-13.el9.x86_64",
    sha256 = "7d9d4d37e86ba94bb941e2dad40c90a157aaa0602f02f3f90e76086515f439be",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libaio-0.3.111-13.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7d9d4d37e86ba94bb941e2dad40c90a157aaa0602f02f3f90e76086515f439be",
    ],
)

rpm(
    name = "libarchive-0__3.5.3-4.el9.aarch64",
    sha256 = "c043954972a8dea0b6cf5d3092c1eee90bb48b3fcb7cedf30aa861dc1d3f402c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libarchive-3.5.3-4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/c043954972a8dea0b6cf5d3092c1eee90bb48b3fcb7cedf30aa861dc1d3f402c",
    ],
)

rpm(
    name = "libarchive-0__3.5.3-4.el9.x86_64",
    sha256 = "4c53176eafd8c449aef704b8fbc2d5401bb7d2ea0a67961956f318f2e9a2c7a4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libarchive-3.5.3-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/4c53176eafd8c449aef704b8fbc2d5401bb7d2ea0a67961956f318f2e9a2c7a4",
    ],
)

rpm(
    name = "libasan-0__11.3.1-4.4.el9.aarch64",
    sha256 = "a0d998edf1330d2989399faeb436e224ef88eb039cc859516aba2a046c8819eb",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libasan-11.3.1-4.4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/a0d998edf1330d2989399faeb436e224ef88eb039cc859516aba2a046c8819eb",
    ],
)

rpm(
    name = "libassuan-0__2.5.5-3.el9.x86_64",
    sha256 = "3f7ab80145768029619033b31406a9aeef8c8f0d42a0c94ad464d8a3405e12b0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libassuan-2.5.5-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/3f7ab80145768029619033b31406a9aeef8c8f0d42a0c94ad464d8a3405e12b0",
    ],
)

rpm(
    name = "libatomic-0__11.3.1-4.4.el9.aarch64",
    sha256 = "afb79748687fb135dd3d0502853ee93d706d29690a2289f9f2a59d49dbac556a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libatomic-11.3.1-4.4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/afb79748687fb135dd3d0502853ee93d706d29690a2289f9f2a59d49dbac556a",
    ],
)

rpm(
    name = "libattr-0__2.5.1-3.el9.aarch64",
    sha256 = "a0101ccea66aef376f4067c1002ebdfb5dbeeecd334047459b3855eff17a6fda",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libattr-2.5.1-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/a0101ccea66aef376f4067c1002ebdfb5dbeeecd334047459b3855eff17a6fda",
    ],
)

rpm(
    name = "libattr-0__2.5.1-3.el9.x86_64",
    sha256 = "d4db095a015e84065f27a642ee7829cd1690041ba8c51501f908cc34760c9409",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libattr-2.5.1-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d4db095a015e84065f27a642ee7829cd1690041ba8c51501f908cc34760c9409",
    ],
)

rpm(
    name = "libbasicobjects-0__0.1.1-53.el9.x86_64",
    sha256 = "14ce3dd811d88dddc4009c12094cd0e52bbcabe0f2463bdfcc4124c620fb13d5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libbasicobjects-0.1.1-53.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/14ce3dd811d88dddc4009c12094cd0e52bbcabe0f2463bdfcc4124c620fb13d5",
    ],
)

rpm(
    name = "libblkid-0__2.37.4-10.el9.aarch64",
    sha256 = "3a41e99e7f18f750a40e4bebe68aa9ab1763250977318a767fd4a07a016dcf51",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libblkid-2.37.4-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/3a41e99e7f18f750a40e4bebe68aa9ab1763250977318a767fd4a07a016dcf51",
    ],
)

rpm(
    name = "libblkid-0__2.37.4-10.el9.x86_64",
    sha256 = "e03fd98c3381691ed843550fa9129337682e5d70a0215c9744283cc653b3d6f9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libblkid-2.37.4-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/e03fd98c3381691ed843550fa9129337682e5d70a0215c9744283cc653b3d6f9",
    ],
)

rpm(
    name = "libbpf-2__1.0.0-2.el9.aarch64",
    sha256 = "8558d9cecee6d874faefbfa72bd06774dcaab885065ee6b35b1dcc60779263a7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libbpf-1.0.0-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/8558d9cecee6d874faefbfa72bd06774dcaab885065ee6b35b1dcc60779263a7",
    ],
)

rpm(
    name = "libbpf-2__1.0.0-2.el9.x86_64",
    sha256 = "fab4a0b62c428759378b4b362158c820cb348b27daf33bf46792ae16aca17b88",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libbpf-1.0.0-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fab4a0b62c428759378b4b362158c820cb348b27daf33bf46792ae16aca17b88",
    ],
)

rpm(
    name = "libburn-0__1.5.4-4.el9.aarch64",
    sha256 = "9a38b538faba01eb3aa59abdbfa05f37705ed6e21cea74fa8cca97f4fe7dad20",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libburn-1.5.4-4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/9a38b538faba01eb3aa59abdbfa05f37705ed6e21cea74fa8cca97f4fe7dad20",
    ],
)

rpm(
    name = "libburn-0__1.5.4-4.el9.x86_64",
    sha256 = "c6bbbaa269d37d0cd29bdd329bf91096112cff6aa623112d6b3c9b3bb365ebaa",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libburn-1.5.4-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c6bbbaa269d37d0cd29bdd329bf91096112cff6aa623112d6b3c9b3bb365ebaa",
    ],
)

rpm(
    name = "libcap-0__2.48-8.el9.aarch64",
    sha256 = "881d4e7729633ce71b1a6bab3a84c1f79d5e7c49ef3ffdc1bc703cdd7ae3cd81",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libcap-2.48-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/881d4e7729633ce71b1a6bab3a84c1f79d5e7c49ef3ffdc1bc703cdd7ae3cd81",
    ],
)

rpm(
    name = "libcap-0__2.48-8.el9.x86_64",
    sha256 = "c41f91075ee8ca480c2631a485bcc74876b9317b4dc9bd66566da32313621bd7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libcap-2.48-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c41f91075ee8ca480c2631a485bcc74876b9317b4dc9bd66566da32313621bd7",
    ],
)

rpm(
    name = "libcap-ng-0__0.8.2-7.el9.aarch64",
    sha256 = "1dfa7208abe1af5522523cabdabb73783ed1df4424dc8846eab8a570d010deaa",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libcap-ng-0.8.2-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/1dfa7208abe1af5522523cabdabb73783ed1df4424dc8846eab8a570d010deaa",
    ],
)

rpm(
    name = "libcap-ng-0__0.8.2-7.el9.x86_64",
    sha256 = "62429b788acfb40dbc9da9951690c11e907e230879c790d139f73d0e85dd76f4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libcap-ng-0.8.2-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/62429b788acfb40dbc9da9951690c11e907e230879c790d139f73d0e85dd76f4",
    ],
)

rpm(
    name = "libcollection-0__0.7.0-53.el9.x86_64",
    sha256 = "07c24fc00d1fd088a7f2b16b6cf70b781aed6ed682f11c4bce3ab76cf56707fd",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libcollection-0.7.0-53.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/07c24fc00d1fd088a7f2b16b6cf70b781aed6ed682f11c4bce3ab76cf56707fd",
    ],
)

rpm(
    name = "libcom_err-0__1.46.5-3.el9.aarch64",
    sha256 = "a735b91094a13612830db66fd2021c9ec86c92697e526068e8b3919111cc2ba8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libcom_err-1.46.5-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/a735b91094a13612830db66fd2021c9ec86c92697e526068e8b3919111cc2ba8",
    ],
)

rpm(
    name = "libcom_err-0__1.46.5-3.el9.x86_64",
    sha256 = "ef9db384c8fbfc0b8676aec1896070dc308cfc0c7b515ebbe556e0fea68318d0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libcom_err-1.46.5-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/ef9db384c8fbfc0b8676aec1896070dc308cfc0c7b515ebbe556e0fea68318d0",
    ],
)

rpm(
    name = "libconfig-0__1.7.2-9.el9.x86_64",
    sha256 = "e0d4d2cf8215404750c3975a19e2b7cd2c9e9e1e5c539d3fd93532775fd2ed16",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libconfig-1.7.2-9.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/e0d4d2cf8215404750c3975a19e2b7cd2c9e9e1e5c539d3fd93532775fd2ed16",
    ],
)

rpm(
    name = "libcurl-minimal-0__7.76.1-23.el9.aarch64",
    sha256 = "6c8bfb094c6b85a0c734f77aa71e70a20303db35f38621c64cd88036e252f4e4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libcurl-minimal-7.76.1-23.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/6c8bfb094c6b85a0c734f77aa71e70a20303db35f38621c64cd88036e252f4e4",
    ],
)

rpm(
    name = "libcurl-minimal-0__7.76.1-23.el9.x86_64",
    sha256 = "2c3b47ffd361c8b55b0af081c8a4c5e6fc23b8c5ce540401ee8e219a5c77a802",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libcurl-minimal-7.76.1-23.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/2c3b47ffd361c8b55b0af081c8a4c5e6fc23b8c5ce540401ee8e219a5c77a802",
    ],
)

rpm(
    name = "libdb-0__5.3.28-53.el9.aarch64",
    sha256 = "65a5743728c6c331dd8aadc9b51f261f90ffa47ffd0cfb448da8bdf28af6dd77",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libdb-5.3.28-53.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/65a5743728c6c331dd8aadc9b51f261f90ffa47ffd0cfb448da8bdf28af6dd77",
    ],
)

rpm(
    name = "libdb-0__5.3.28-53.el9.x86_64",
    sha256 = "3a44d15d695944bde4e7290800b815f98bfd9cd6f6f868cec3e8991606f556d5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libdb-5.3.28-53.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/3a44d15d695944bde4e7290800b815f98bfd9cd6f6f868cec3e8991606f556d5",
    ],
)

rpm(
    name = "libeconf-0__0.4.1-2.el9.aarch64",
    sha256 = "082dff130121fcdb7cb3fd432de482075b5003e0d95ff4ab6d8ba02404b69d6b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libeconf-0.4.1-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/082dff130121fcdb7cb3fd432de482075b5003e0d95ff4ab6d8ba02404b69d6b",
    ],
)

rpm(
    name = "libeconf-0__0.4.1-2.el9.x86_64",
    sha256 = "1d6fe169e74daff38ad5b0d6424c4d1b14545d5974c39e4421d20838a68f5892",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libeconf-0.4.1-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/1d6fe169e74daff38ad5b0d6424c4d1b14545d5974c39e4421d20838a68f5892",
    ],
)

rpm(
    name = "libev-0__4.33-5.el9.x86_64",
    sha256 = "9ee87c7d34e341bc7b136125ef5f1429a0b5fadaffcf888ab896b2c62c2b4e8d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libev-4.33-5.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/9ee87c7d34e341bc7b136125ef5f1429a0b5fadaffcf888ab896b2c62c2b4e8d",
    ],
)

rpm(
    name = "libevent-0__2.1.12-6.el9.aarch64",
    sha256 = "5ff00c047204190e3b2ee19f81d644c8f82ea7e8d1f36fdaaf6483f0fa3b3339",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libevent-2.1.12-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/5ff00c047204190e3b2ee19f81d644c8f82ea7e8d1f36fdaaf6483f0fa3b3339",
    ],
)

rpm(
    name = "libevent-0__2.1.12-6.el9.x86_64",
    sha256 = "82179f6f214ddf523e143c16c3474ccf8832551c6305faf89edfbd83b3424d48",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libevent-2.1.12-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/82179f6f214ddf523e143c16c3474ccf8832551c6305faf89edfbd83b3424d48",
    ],
)

rpm(
    name = "libfdisk-0__2.37.4-10.el9.aarch64",
    sha256 = "e6bc17e44b15edf238d98490c5983a2f86923839aea4968f8fe408901d6dcb6b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libfdisk-2.37.4-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/e6bc17e44b15edf238d98490c5983a2f86923839aea4968f8fe408901d6dcb6b",
    ],
)

rpm(
    name = "libfdisk-0__2.37.4-10.el9.x86_64",
    sha256 = "ac96f05b0e92ca732ca40ac86088b3b74fb5b6c513a80094300e35d6b6b989c4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libfdisk-2.37.4-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/ac96f05b0e92ca732ca40ac86088b3b74fb5b6c513a80094300e35d6b6b989c4",
    ],
)

rpm(
    name = "libfdt-0__1.6.0-7.el9.aarch64",
    sha256 = "19cd82e2bbdd6254169b267e645564acd0911e02fafaf6e3ad9893cd1f9d3d67",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libfdt-1.6.0-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/19cd82e2bbdd6254169b267e645564acd0911e02fafaf6e3ad9893cd1f9d3d67",
    ],
)

rpm(
    name = "libfdt-0__1.6.0-7.el9.x86_64",
    sha256 = "a071b9d517505a2ff8642de7ac094faa689b96122c0a3e9ce86933aa1dea525f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libfdt-1.6.0-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/a071b9d517505a2ff8642de7ac094faa689b96122c0a3e9ce86933aa1dea525f",
    ],
)

rpm(
    name = "libffi-0__3.4.2-7.el9.aarch64",
    sha256 = "6a42002c0b63a3c4d1e8da5cdf4822f442a7b458d80e69673715715d38ea977d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libffi-3.4.2-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/6a42002c0b63a3c4d1e8da5cdf4822f442a7b458d80e69673715715d38ea977d",
    ],
)

rpm(
    name = "libffi-0__3.4.2-7.el9.x86_64",
    sha256 = "f0ac4b6454d4018833dd10e3f437d8271c7c6a628d99b37e75b83af890b86bc4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libffi-3.4.2-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/f0ac4b6454d4018833dd10e3f437d8271c7c6a628d99b37e75b83af890b86bc4",
    ],
)

rpm(
    name = "libgcc-0__11.3.1-4.4.el9.aarch64",
    sha256 = "64f0951f780e09847f447d6996c8b6da7872b746113731c41c5e44e6306509cc",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libgcc-11.3.1-4.4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/64f0951f780e09847f447d6996c8b6da7872b746113731c41c5e44e6306509cc",
    ],
)

rpm(
    name = "libgcc-0__11.3.1-4.4.el9.x86_64",
    sha256 = "5a488d40fefa0b5abc0ab9db74b48c25f91816a69f6a5ad8bff562f2b26cdc1e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libgcc-11.3.1-4.4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/5a488d40fefa0b5abc0ab9db74b48c25f91816a69f6a5ad8bff562f2b26cdc1e",
    ],
)

rpm(
    name = "libgcrypt-0__1.10.0-10.el9.aarch64",
    sha256 = "b5a90cb5a86ee956da8439362d8547342f240e71674e4703d87f27736dbede14",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libgcrypt-1.10.0-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/b5a90cb5a86ee956da8439362d8547342f240e71674e4703d87f27736dbede14",
    ],
)

rpm(
    name = "libgcrypt-0__1.10.0-10.el9.x86_64",
    sha256 = "186ae69a1f72d3992f2f65a4cc91da856a54475f4762a69f3b5ca5d350e7edb3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libgcrypt-1.10.0-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/186ae69a1f72d3992f2f65a4cc91da856a54475f4762a69f3b5ca5d350e7edb3",
    ],
)

rpm(
    name = "libgomp-0__11.3.1-4.4.el9.aarch64",
    sha256 = "76257d4bb071b5aeec034ac48c9ed256b1dd80d31fe21a1781655b0091cf0389",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libgomp-11.3.1-4.4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/76257d4bb071b5aeec034ac48c9ed256b1dd80d31fe21a1781655b0091cf0389",
    ],
)

rpm(
    name = "libgomp-0__11.3.1-4.4.el9.x86_64",
    sha256 = "820554764219bfc0d4edcd0620e993dcc00c9cd7a196618c49d24f0e8d14f72e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libgomp-11.3.1-4.4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/820554764219bfc0d4edcd0620e993dcc00c9cd7a196618c49d24f0e8d14f72e",
    ],
)

rpm(
    name = "libgpg-error-0__1.42-5.el9.aarch64",
    sha256 = "ffeb04823b5317c7e016542c8ecc5180c7824f8b59a180f2434fd096a34a9105",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libgpg-error-1.42-5.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/ffeb04823b5317c7e016542c8ecc5180c7824f8b59a180f2434fd096a34a9105",
    ],
)

rpm(
    name = "libgpg-error-0__1.42-5.el9.x86_64",
    sha256 = "a1883804c376f737109f4dff06077d1912b90150a732d11be7bc5b3b67e512fe",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libgpg-error-1.42-5.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/a1883804c376f737109f4dff06077d1912b90150a732d11be7bc5b3b67e512fe",
    ],
)

rpm(
    name = "libguestfs-1__1.48.4-4.el9.x86_64",
    sha256 = "ab50fdd378fb6fad46a61cb6d33ac582b7d5d9e5c4fcf3e8dfd55e8a630fd05f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libguestfs-1.48.4-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/ab50fdd378fb6fad46a61cb6d33ac582b7d5d9e5c4fcf3e8dfd55e8a630fd05f",
    ],
)

rpm(
    name = "libibverbs-0__44.0-2.el9.aarch64",
    sha256 = "32465080635726202a44a2a9ef09240aa621ac4980376a99f68e431a145a77f3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libibverbs-44.0-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/32465080635726202a44a2a9ef09240aa621ac4980376a99f68e431a145a77f3",
    ],
)

rpm(
    name = "libibverbs-0__44.0-2.el9.x86_64",
    sha256 = "0b84128e8cbefa4b76e48fd52622c81c2657baeeea293c9b39b17383d85c7a17",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libibverbs-44.0-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/0b84128e8cbefa4b76e48fd52622c81c2657baeeea293c9b39b17383d85c7a17",
    ],
)

rpm(
    name = "libidn2-0__2.3.0-7.el9.aarch64",
    sha256 = "6ed96112059449aa37b99d4d4e3b5d089c34afefbd9b618691bed8c206c4d441",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libidn2-2.3.0-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/6ed96112059449aa37b99d4d4e3b5d089c34afefbd9b618691bed8c206c4d441",
    ],
)

rpm(
    name = "libidn2-0__2.3.0-7.el9.x86_64",
    sha256 = "f7fa1ad2fcd86beea5d4d965994c21dc98f47871faff14f73940190c754ab244",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libidn2-2.3.0-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/f7fa1ad2fcd86beea5d4d965994c21dc98f47871faff14f73940190c754ab244",
    ],
)

rpm(
    name = "libini_config-0__1.3.1-53.el9.x86_64",
    sha256 = "fb7dbaeb7c172663cab3029c4efaf80230bcba4abf1604cc6cc00993b5d9659e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libini_config-1.3.1-53.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fb7dbaeb7c172663cab3029c4efaf80230bcba4abf1604cc6cc00993b5d9659e",
    ],
)

rpm(
    name = "libisoburn-0__1.5.4-4.el9.aarch64",
    sha256 = "73b53499b7cd070a899a202385ca3da1ae37e7bb65123767e6d74dbb432f7a08",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libisoburn-1.5.4-4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/73b53499b7cd070a899a202385ca3da1ae37e7bb65123767e6d74dbb432f7a08",
    ],
)

rpm(
    name = "libisoburn-0__1.5.4-4.el9.x86_64",
    sha256 = "922f3d45899dfdcebf4cc9b5b82f31be240f76098ffbdbcb3291b4a77dcbbab7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libisoburn-1.5.4-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/922f3d45899dfdcebf4cc9b5b82f31be240f76098ffbdbcb3291b4a77dcbbab7",
    ],
)

rpm(
    name = "libisofs-0__1.5.4-4.el9.aarch64",
    sha256 = "0f4c8376add266f01328ea001c580ef9258c0ce39c26906226871c934a159e88",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libisofs-1.5.4-4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/0f4c8376add266f01328ea001c580ef9258c0ce39c26906226871c934a159e88",
    ],
)

rpm(
    name = "libisofs-0__1.5.4-4.el9.x86_64",
    sha256 = "78abca0dc6134189106ff550986cc059dc0edea129e572a742d2cc0b934c2d13",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libisofs-1.5.4-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/78abca0dc6134189106ff550986cc059dc0edea129e572a742d2cc0b934c2d13",
    ],
)

rpm(
    name = "libksba-0__1.5.1-6.el9.x86_64",
    sha256 = "ff76d9798e2f040fed715968a9e67f6d5cfef59671e07575fc8d6510126b5340",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libksba-1.5.1-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/ff76d9798e2f040fed715968a9e67f6d5cfef59671e07575fc8d6510126b5340",
    ],
)

rpm(
    name = "libmnl-0__1.0.4-15.el9.aarch64",
    sha256 = "a3e80b22d57f0e2843e37eee0440a9bae92e4a0cbe75b13520be7616afd70e78",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libmnl-1.0.4-15.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/a3e80b22d57f0e2843e37eee0440a9bae92e4a0cbe75b13520be7616afd70e78",
    ],
)

rpm(
    name = "libmnl-0__1.0.4-15.el9.x86_64",
    sha256 = "a70fdda85cd771ef5bf5b17c2996e4ff4d21c2e5b1eece1764a87f12e720ab68",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libmnl-1.0.4-15.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/a70fdda85cd771ef5bf5b17c2996e4ff4d21c2e5b1eece1764a87f12e720ab68",
    ],
)

rpm(
    name = "libmount-0__2.37.4-10.el9.aarch64",
    sha256 = "d689d25556654b69ddc38e975207f2d4152c98788e41058376564165cb55bd59",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libmount-2.37.4-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/d689d25556654b69ddc38e975207f2d4152c98788e41058376564165cb55bd59",
    ],
)

rpm(
    name = "libmount-0__2.37.4-10.el9.x86_64",
    sha256 = "7c88405577b17476a0204b12b05c261fb1eed87b77ccd1ec78fe3e6b03e4351f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libmount-2.37.4-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7c88405577b17476a0204b12b05c261fb1eed87b77ccd1ec78fe3e6b03e4351f",
    ],
)

rpm(
    name = "libmpc-0__1.2.1-4.el9.aarch64",
    sha256 = "489bd89037b1a77d696e391315c740f185e6447aacdb1d7fe84b411491c34b88",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libmpc-1.2.1-4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/489bd89037b1a77d696e391315c740f185e6447aacdb1d7fe84b411491c34b88",
    ],
)

rpm(
    name = "libmpc-0__1.2.1-4.el9.x86_64",
    sha256 = "207e758fadd4779cb11b91a78446f098d0a95b782f30a24c0e998fe08e2561df",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libmpc-1.2.1-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/207e758fadd4779cb11b91a78446f098d0a95b782f30a24c0e998fe08e2561df",
    ],
)

rpm(
    name = "libnetfilter_conntrack-0__1.0.9-1.el9.aarch64",
    sha256 = "6871a3371b5a9a8239606efd453b59b274040e9d8d8f0c18bdffa7264db64264",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libnetfilter_conntrack-1.0.9-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/6871a3371b5a9a8239606efd453b59b274040e9d8d8f0c18bdffa7264db64264",
    ],
)

rpm(
    name = "libnetfilter_conntrack-0__1.0.9-1.el9.x86_64",
    sha256 = "f81a0188964268ae9e1d53d99dba3ef96a65fe2fb00bc8fe6c39cedfdd364f44",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libnetfilter_conntrack-1.0.9-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/f81a0188964268ae9e1d53d99dba3ef96a65fe2fb00bc8fe6c39cedfdd364f44",
    ],
)

rpm(
    name = "libnfnetlink-0__1.0.1-21.el9.aarch64",
    sha256 = "682c4cca565ce483ff0749dbb39b154bc080ac531c418d05890e454114c11821",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libnfnetlink-1.0.1-21.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/682c4cca565ce483ff0749dbb39b154bc080ac531c418d05890e454114c11821",
    ],
)

rpm(
    name = "libnfnetlink-0__1.0.1-21.el9.x86_64",
    sha256 = "64f54f412cc0ee6fe82be7557f471a06f6bf1f5bba1d6fe0ad1879e5a62d7c95",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libnfnetlink-1.0.1-21.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/64f54f412cc0ee6fe82be7557f471a06f6bf1f5bba1d6fe0ad1879e5a62d7c95",
    ],
)

rpm(
    name = "libnfsidmap-1__2.5.4-18.el9.x86_64",
    sha256 = "dcedd5199d03c1aea13bbd45faa8b383f08666357a9839c9e136429ea9b0bb29",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libnfsidmap-2.5.4-18.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/dcedd5199d03c1aea13bbd45faa8b383f08666357a9839c9e136429ea9b0bb29",
    ],
)

rpm(
    name = "libnftnl-0__1.2.2-1.el9.aarch64",
    sha256 = "6e2dac1414db86b13f0efbca18bd0128a122ba2b814faed1bce309200304cc86",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libnftnl-1.2.2-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/6e2dac1414db86b13f0efbca18bd0128a122ba2b814faed1bce309200304cc86",
    ],
)

rpm(
    name = "libnftnl-0__1.2.2-1.el9.x86_64",
    sha256 = "fd75863a6dd1be0e7f1b7eed3e5f13a0efead33ba9bb05b0f8430574aa804783",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libnftnl-1.2.2-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fd75863a6dd1be0e7f1b7eed3e5f13a0efead33ba9bb05b0f8430574aa804783",
    ],
)

rpm(
    name = "libnghttp2-0__1.43.0-5.el9.aarch64",
    sha256 = "702abf0c5b1574b828132e4dbea17ad7099034db18f47fd1ac84b4d9534dcfea",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libnghttp2-1.43.0-5.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/702abf0c5b1574b828132e4dbea17ad7099034db18f47fd1ac84b4d9534dcfea",
    ],
)

rpm(
    name = "libnghttp2-0__1.43.0-5.el9.x86_64",
    sha256 = "58c5d589ee370951b98e908ac05a5a6154d52dbb8cf2067583ccdd10cdf099bf",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libnghttp2-1.43.0-5.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/58c5d589ee370951b98e908ac05a5a6154d52dbb8cf2067583ccdd10cdf099bf",
    ],
)

rpm(
    name = "libnl3-0__3.7.0-1.el9.aarch64",
    sha256 = "5f8ede2ff552132a369b43e7babfd5e08e0dc46b5c659a665f188dc497cb0415",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libnl3-3.7.0-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/5f8ede2ff552132a369b43e7babfd5e08e0dc46b5c659a665f188dc497cb0415",
    ],
)

rpm(
    name = "libnl3-0__3.7.0-1.el9.x86_64",
    sha256 = "8abf9bf3f62df66aeed157fc9f9494a2ea792eb11eb221caa17ce7f97330a2f3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libnl3-3.7.0-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/8abf9bf3f62df66aeed157fc9f9494a2ea792eb11eb221caa17ce7f97330a2f3",
    ],
)

rpm(
    name = "libpath_utils-0__0.2.1-53.el9.x86_64",
    sha256 = "0a2519647ef22df7c975fa2851da713e67361ff33f2bff05f91cb588b2722772",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libpath_utils-0.2.1-53.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/0a2519647ef22df7c975fa2851da713e67361ff33f2bff05f91cb588b2722772",
    ],
)

rpm(
    name = "libpcap-14__1.10.0-4.el9.aarch64",
    sha256 = "c1827185bde78c34817a75c79522963c76cd07585eeeb6961e58c6ddadc69333",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libpcap-1.10.0-4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/c1827185bde78c34817a75c79522963c76cd07585eeeb6961e58c6ddadc69333",
    ],
)

rpm(
    name = "libpcap-14__1.10.0-4.el9.x86_64",
    sha256 = "c76c9887f6b9d218300b24f1adee1b0d9104d25152df3fcd005002d12e12399e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libpcap-1.10.0-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c76c9887f6b9d218300b24f1adee1b0d9104d25152df3fcd005002d12e12399e",
    ],
)

rpm(
    name = "libpkgconf-0__1.7.3-10.el9.aarch64",
    sha256 = "ad86227404ab0df04f1b98f74921a77c4068251da74067d3633cc1c43fee4a9b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libpkgconf-1.7.3-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/ad86227404ab0df04f1b98f74921a77c4068251da74067d3633cc1c43fee4a9b",
    ],
)

rpm(
    name = "libpkgconf-0__1.7.3-10.el9.x86_64",
    sha256 = "2dc8b201f4e24ca65fe6389fec8901eb84d48519cc44a6b0e474d7859370f389",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libpkgconf-1.7.3-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/2dc8b201f4e24ca65fe6389fec8901eb84d48519cc44a6b0e474d7859370f389",
    ],
)

rpm(
    name = "libpmem-0__1.12.1-1.el9.x86_64",
    sha256 = "5377dcb3b4ca48eb056a998d3a684eb68e8d059e2a26844cda8535d8f125fc83",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libpmem-1.12.1-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/5377dcb3b4ca48eb056a998d3a684eb68e8d059e2a26844cda8535d8f125fc83",
    ],
)

rpm(
    name = "libpng-2__1.6.37-12.el9.aarch64",
    sha256 = "99f9eca159e41e315b9fe48ec6c6d1d7a944bd5d8fc0b308aba779a6608b3777",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libpng-1.6.37-12.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/99f9eca159e41e315b9fe48ec6c6d1d7a944bd5d8fc0b308aba779a6608b3777",
    ],
)

rpm(
    name = "libpng-2__1.6.37-12.el9.x86_64",
    sha256 = "b3f3a689918dc50a9bc41c33abf1a36bdb8e4a707daac77a91e0814407b07ae3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libpng-1.6.37-12.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b3f3a689918dc50a9bc41c33abf1a36bdb8e4a707daac77a91e0814407b07ae3",
    ],
)

rpm(
    name = "libpwquality-0__1.4.4-8.el9.aarch64",
    sha256 = "3c22a268ce022cb4722aa2d35a95c1174778f424fbf29e98990801651d468aeb",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libpwquality-1.4.4-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/3c22a268ce022cb4722aa2d35a95c1174778f424fbf29e98990801651d468aeb",
    ],
)

rpm(
    name = "libpwquality-0__1.4.4-8.el9.x86_64",
    sha256 = "93f00e5efac1e3f1ecbc0d6a4c068772cb12912cd20c9ea58716d6c0cd004886",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libpwquality-1.4.4-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/93f00e5efac1e3f1ecbc0d6a4c068772cb12912cd20c9ea58716d6c0cd004886",
    ],
)

rpm(
    name = "librdmacm-0__44.0-2.el9.aarch64",
    sha256 = "37025c1ac57da56bd5ce2d5f440e4a8bf51d5cf4a30af7e3ebc0562e6804151b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/librdmacm-44.0-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/37025c1ac57da56bd5ce2d5f440e4a8bf51d5cf4a30af7e3ebc0562e6804151b",
    ],
)

rpm(
    name = "librdmacm-0__44.0-2.el9.x86_64",
    sha256 = "759f3be69c214ab5d503df1c4722f48ecf8494e8912ec97a4d3cc12b5ac90b81",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/librdmacm-44.0-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/759f3be69c214ab5d503df1c4722f48ecf8494e8912ec97a4d3cc12b5ac90b81",
    ],
)

rpm(
    name = "libref_array-0__0.1.5-53.el9.x86_64",
    sha256 = "7a7eaf030a25e866148daa6b38ac6f49afeba63b66f11040cc7b5b5522977d1e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libref_array-0.1.5-53.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7a7eaf030a25e866148daa6b38ac6f49afeba63b66f11040cc7b5b5522977d1e",
    ],
)

rpm(
    name = "libseccomp-0__2.5.2-2.el9.aarch64",
    sha256 = "ee31abd3d1325b05c5ba336158ba3b235a718a99ad5cec5e6ab498ca99b688b5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libseccomp-2.5.2-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/ee31abd3d1325b05c5ba336158ba3b235a718a99ad5cec5e6ab498ca99b688b5",
    ],
)

rpm(
    name = "libseccomp-0__2.5.2-2.el9.x86_64",
    sha256 = "d5c1c4473ebf5fd9c605eb866118d7428cdec9b188db18e45545801cc2a689c3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libseccomp-2.5.2-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d5c1c4473ebf5fd9c605eb866118d7428cdec9b188db18e45545801cc2a689c3",
    ],
)

rpm(
    name = "libselinux-0__3.5-1.el9.aarch64",
    sha256 = "1968d3199e772d0476df14b54b5f85a23329befc1ff7597f45d457b8dc9b0ddd",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libselinux-3.5-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/1968d3199e772d0476df14b54b5f85a23329befc1ff7597f45d457b8dc9b0ddd",
    ],
)

rpm(
    name = "libselinux-0__3.5-1.el9.x86_64",
    sha256 = "7e7309502af6056593e4c247f1829fd46cc7480ed46da020446ea6c2f1553bd1",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libselinux-3.5-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7e7309502af6056593e4c247f1829fd46cc7480ed46da020446ea6c2f1553bd1",
    ],
)

rpm(
    name = "libselinux-utils-0__3.5-1.el9.aarch64",
    sha256 = "94546ba5175d89231654f3dd12fea21b967bb58c8edbee605dec09c69e260ff7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libselinux-utils-3.5-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/94546ba5175d89231654f3dd12fea21b967bb58c8edbee605dec09c69e260ff7",
    ],
)

rpm(
    name = "libselinux-utils-0__3.5-1.el9.x86_64",
    sha256 = "ab57f8b616e7a29cdb72d040b19fa001e68a29f0f8b17e151f0652d6111c66a7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libselinux-utils-3.5-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/ab57f8b616e7a29cdb72d040b19fa001e68a29f0f8b17e151f0652d6111c66a7",
    ],
)

rpm(
    name = "libsemanage-0__3.5-1.el9.aarch64",
    sha256 = "2ae9453ae0afb19eb47afcba5bc19ef913ac019c796b2cf125b23c0f9aa86526",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libsemanage-3.5-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/2ae9453ae0afb19eb47afcba5bc19ef913ac019c796b2cf125b23c0f9aa86526",
    ],
)

rpm(
    name = "libsemanage-0__3.5-1.el9.x86_64",
    sha256 = "5ce97fe99a52cb203c9a0cbd1da273e1b11a6846b4291fc0f0273cd6fc99b38a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libsemanage-3.5-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/5ce97fe99a52cb203c9a0cbd1da273e1b11a6846b4291fc0f0273cd6fc99b38a",
    ],
)

rpm(
    name = "libsepol-0__3.5-1.el9.aarch64",
    sha256 = "70e6cb0c9d177d512431a1a18ecb7f0bced1e08940df5463961de59fc243ab62",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libsepol-3.5-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/70e6cb0c9d177d512431a1a18ecb7f0bced1e08940df5463961de59fc243ab62",
    ],
)

rpm(
    name = "libsepol-0__3.5-1.el9.x86_64",
    sha256 = "90428114387b69b45fcd7014b219a44ffd89cfecb3bb47c94ca29ab7dce5b940",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libsepol-3.5-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/90428114387b69b45fcd7014b219a44ffd89cfecb3bb47c94ca29ab7dce5b940",
    ],
)

rpm(
    name = "libsigsegv-0__2.13-4.el9.aarch64",
    sha256 = "097399718ae50fb03fde85fa151c060c50445a1a5af185052cac6b92d6fdcdae",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libsigsegv-2.13-4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/097399718ae50fb03fde85fa151c060c50445a1a5af185052cac6b92d6fdcdae",
    ],
)

rpm(
    name = "libsigsegv-0__2.13-4.el9.x86_64",
    sha256 = "931bd0ec7050e8c3b37a9bfb489e30af32486a3c77203f1e9113eeceaa3b0a3a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libsigsegv-2.13-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/931bd0ec7050e8c3b37a9bfb489e30af32486a3c77203f1e9113eeceaa3b0a3a",
    ],
)

rpm(
    name = "libslirp-0__4.4.0-7.el9.aarch64",
    sha256 = "321ef98abb278174e60823b5f032ef8f5bee45d67a0e2b0a56e08e6ae8a7381b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libslirp-4.4.0-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/321ef98abb278174e60823b5f032ef8f5bee45d67a0e2b0a56e08e6ae8a7381b",
    ],
)

rpm(
    name = "libslirp-0__4.4.0-7.el9.x86_64",
    sha256 = "4d7383a18c393e909d037f64c35a8d5d01c559032a3bd760a77844986d57062a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libslirp-4.4.0-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/4d7383a18c393e909d037f64c35a8d5d01c559032a3bd760a77844986d57062a",
    ],
)

rpm(
    name = "libsmartcols-0__2.37.4-10.el9.aarch64",
    sha256 = "1e73d04db2be78965b04e065afc6c90dddf1223df985cd37d3c101d54ccba5d3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libsmartcols-2.37.4-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/1e73d04db2be78965b04e065afc6c90dddf1223df985cd37d3c101d54ccba5d3",
    ],
)

rpm(
    name = "libsmartcols-0__2.37.4-10.el9.x86_64",
    sha256 = "fddfa87a98f67e3eb5b1c1a1a4f2d5614772fef6ccbf5a9abbe4783387fe8413",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libsmartcols-2.37.4-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fddfa87a98f67e3eb5b1c1a1a4f2d5614772fef6ccbf5a9abbe4783387fe8413",
    ],
)

rpm(
    name = "libss-0__1.46.5-3.el9.aarch64",
    sha256 = "aa55b0ee8bedeb59bd02534f4906bc8f01d79eacad833a278c25bf8841547bb0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libss-1.46.5-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/aa55b0ee8bedeb59bd02534f4906bc8f01d79eacad833a278c25bf8841547bb0",
    ],
)

rpm(
    name = "libss-0__1.46.5-3.el9.x86_64",
    sha256 = "bf0e9aee3f87c9c9e660a03b879f958ef41c3e94d110af2d97b42cac2a1bde56",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libss-1.46.5-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/bf0e9aee3f87c9c9e660a03b879f958ef41c3e94d110af2d97b42cac2a1bde56",
    ],
)

rpm(
    name = "libssh-0__0.10.4-8.el9.aarch64",
    sha256 = "c7ceb5871d07eeb3375813b3d4f5aeef89cece94a9a7665b00fa93ccb6b72da5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libssh-0.10.4-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/c7ceb5871d07eeb3375813b3d4f5aeef89cece94a9a7665b00fa93ccb6b72da5",
    ],
)

rpm(
    name = "libssh-0__0.10.4-8.el9.x86_64",
    sha256 = "f3296048e8388114a109f9fc43b492de4fa7b0b56a5eebf22bb2165ba911de4a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libssh-0.10.4-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/f3296048e8388114a109f9fc43b492de4fa7b0b56a5eebf22bb2165ba911de4a",
    ],
)

rpm(
    name = "libssh-config-0__0.10.4-8.el9.aarch64",
    sha256 = "67d46454fd72db03eeef84af017dc33dd35c484f59e5fbad195ed96ae9f4ef83",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libssh-config-0.10.4-8.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/67d46454fd72db03eeef84af017dc33dd35c484f59e5fbad195ed96ae9f4ef83",
    ],
)

rpm(
    name = "libssh-config-0__0.10.4-8.el9.x86_64",
    sha256 = "67d46454fd72db03eeef84af017dc33dd35c484f59e5fbad195ed96ae9f4ef83",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libssh-config-0.10.4-8.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/67d46454fd72db03eeef84af017dc33dd35c484f59e5fbad195ed96ae9f4ef83",
    ],
)

rpm(
    name = "libsss_idmap-0__2.8.2-2.el9.aarch64",
    sha256 = "1821afa345eb57348510249440e5c42c99128670e097e48aa0ff40321c2bb20f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libsss_idmap-2.8.2-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/1821afa345eb57348510249440e5c42c99128670e097e48aa0ff40321c2bb20f",
    ],
)

rpm(
    name = "libsss_idmap-0__2.8.2-2.el9.x86_64",
    sha256 = "d2f2f490cdbe86ccbb1be9d3d63da4d7ba7ee50c72fb299a9bd5783981d947e5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libsss_idmap-2.8.2-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d2f2f490cdbe86ccbb1be9d3d63da4d7ba7ee50c72fb299a9bd5783981d947e5",
    ],
)

rpm(
    name = "libsss_nss_idmap-0__2.8.2-2.el9.aarch64",
    sha256 = "91f865966b559a29309ebb7f04bd640b8cb2e2f74e77e4fadb552de01c70c0a5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libsss_nss_idmap-2.8.2-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/91f865966b559a29309ebb7f04bd640b8cb2e2f74e77e4fadb552de01c70c0a5",
    ],
)

rpm(
    name = "libsss_nss_idmap-0__2.8.2-2.el9.x86_64",
    sha256 = "82c9533257c753d974c55dacd45d2dc6ed1d13292f900877fd912404a7e665ed",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libsss_nss_idmap-2.8.2-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/82c9533257c753d974c55dacd45d2dc6ed1d13292f900877fd912404a7e665ed",
    ],
)

rpm(
    name = "libstdc__plus____plus__-0__11.3.1-4.4.el9.aarch64",
    sha256 = "efffbed76cfb731a7abb0de31857e27b410edd21c18d5f274a9908c3c0df90f7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libstdc++-11.3.1-4.4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/efffbed76cfb731a7abb0de31857e27b410edd21c18d5f274a9908c3c0df90f7",
    ],
)

rpm(
    name = "libstdc__plus____plus__-0__11.3.1-4.4.el9.x86_64",
    sha256 = "f41eae2eff07dfc79e86480928e2e07d329bb81e6ff1ad4350c25613d6a80c7e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libstdc++-11.3.1-4.4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/f41eae2eff07dfc79e86480928e2e07d329bb81e6ff1ad4350c25613d6a80c7e",
    ],
)

rpm(
    name = "libtasn1-0__4.16.0-8.el9.aarch64",
    sha256 = "1046c07821506ef6a84291b093de0d62dcc9873142e1ac2c66aaa72abd08532c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libtasn1-4.16.0-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/1046c07821506ef6a84291b093de0d62dcc9873142e1ac2c66aaa72abd08532c",
    ],
)

rpm(
    name = "libtasn1-0__4.16.0-8.el9.x86_64",
    sha256 = "c8b13c9e1292de474e76ab80f230f86cce2e8f5f53592e168bdcaa604ed1b37d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libtasn1-4.16.0-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c8b13c9e1292de474e76ab80f230f86cce2e8f5f53592e168bdcaa604ed1b37d",
    ],
)

rpm(
    name = "libtirpc-0__1.3.3-1.el9.aarch64",
    sha256 = "7ccc9d433def3922b81c136a1e3c6bd5882f16b80915b2b92145c7cca4eb1b6b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libtirpc-1.3.3-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/7ccc9d433def3922b81c136a1e3c6bd5882f16b80915b2b92145c7cca4eb1b6b",
    ],
)

rpm(
    name = "libtirpc-0__1.3.3-1.el9.x86_64",
    sha256 = "a8e744f25465ade2ebfbda123e1f9b6db6caa02747aa7274f90bcc3c7599f17b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libtirpc-1.3.3-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/a8e744f25465ade2ebfbda123e1f9b6db6caa02747aa7274f90bcc3c7599f17b",
    ],
)

rpm(
    name = "libtpms-0__0.9.1-3.20211126git1ff6fe1f43.el9.aarch64",
    sha256 = "7f3313bf113fce33ece6b942942a8126713289a545da9eafbb508e9ff6008be2",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libtpms-0.9.1-3.20211126git1ff6fe1f43.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/7f3313bf113fce33ece6b942942a8126713289a545da9eafbb508e9ff6008be2",
    ],
)

rpm(
    name = "libtpms-0__0.9.1-3.20211126git1ff6fe1f43.el9.x86_64",
    sha256 = "4ed3052085b118c19f44c3ce29749895627acc590e45acc0722da5d53582afe7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libtpms-0.9.1-3.20211126git1ff6fe1f43.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/4ed3052085b118c19f44c3ce29749895627acc590e45acc0722da5d53582afe7",
    ],
)

rpm(
    name = "libubsan-0__11.3.1-4.4.el9.aarch64",
    sha256 = "0c23ef212b0c233db35697f3eb1cd5b02c58acc54f7ce5c27face0d0f76b7a7a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libubsan-11.3.1-4.4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/0c23ef212b0c233db35697f3eb1cd5b02c58acc54f7ce5c27face0d0f76b7a7a",
    ],
)

rpm(
    name = "libunistring-0__0.9.10-15.el9.aarch64",
    sha256 = "09381b23c9d2343592b8b565dcbb23d055999ab1e521aa802b6d40a682b80e42",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libunistring-0.9.10-15.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/09381b23c9d2343592b8b565dcbb23d055999ab1e521aa802b6d40a682b80e42",
    ],
)

rpm(
    name = "libunistring-0__0.9.10-15.el9.x86_64",
    sha256 = "11e736e44265d2d0ca0afa4c11cfe0856553c4124e534fb616e6ab61c9b59e46",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libunistring-0.9.10-15.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/11e736e44265d2d0ca0afa4c11cfe0856553c4124e534fb616e6ab61c9b59e46",
    ],
)

rpm(
    name = "libusbx-0__1.0.26-1.el9.aarch64",
    sha256 = "f008b954b622f27dbc5b0c8f3633589c844b5428a1dfe84ca96d42a72dae707c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libusbx-1.0.26-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/f008b954b622f27dbc5b0c8f3633589c844b5428a1dfe84ca96d42a72dae707c",
    ],
)

rpm(
    name = "libusbx-0__1.0.26-1.el9.x86_64",
    sha256 = "bfc8e2bfbcc0e6aaa4e4e665e52ebdc93fb84f7bf00be4640df0fa6df9cbf042",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libusbx-1.0.26-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/bfc8e2bfbcc0e6aaa4e4e665e52ebdc93fb84f7bf00be4640df0fa6df9cbf042",
    ],
)

rpm(
    name = "libutempter-0__1.2.1-6.el9.aarch64",
    sha256 = "65cd8c3813afc69dd2ea9eeb6e2fc7db4a7d626b51efe376b8000dfdaa10402a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libutempter-1.2.1-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/65cd8c3813afc69dd2ea9eeb6e2fc7db4a7d626b51efe376b8000dfdaa10402a",
    ],
)

rpm(
    name = "libutempter-0__1.2.1-6.el9.x86_64",
    sha256 = "fab361a9cba04490fd8b5664049983d1e57ebf7c1080804726ba600708524125",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libutempter-1.2.1-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fab361a9cba04490fd8b5664049983d1e57ebf7c1080804726ba600708524125",
    ],
)

rpm(
    name = "libuuid-0__2.37.4-10.el9.aarch64",
    sha256 = "fa43eb58292c9663e71e800bf54e3600bc9f66244cef85b1b4a1b91ab418685d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libuuid-2.37.4-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/fa43eb58292c9663e71e800bf54e3600bc9f66244cef85b1b4a1b91ab418685d",
    ],
)

rpm(
    name = "libuuid-0__2.37.4-10.el9.x86_64",
    sha256 = "e23313a33b8c07e319c83fc2cd3e6cc5febeb2f7ad6551998389f626bde98ae0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libuuid-2.37.4-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/e23313a33b8c07e319c83fc2cd3e6cc5febeb2f7ad6551998389f626bde98ae0",
    ],
)

rpm(
    name = "libverto-0__0.3.2-3.el9.aarch64",
    sha256 = "1190ea8310b0dab3ebbade3180b4c2cf7064e90c894e5415711d7751e709be8a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libverto-0.3.2-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/1190ea8310b0dab3ebbade3180b4c2cf7064e90c894e5415711d7751e709be8a",
    ],
)

rpm(
    name = "libverto-0__0.3.2-3.el9.x86_64",
    sha256 = "c55578b84f169c4ed79b2d50ea03fd1817007e35062c9fe7a58e6cad025f3b24",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libverto-0.3.2-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c55578b84f169c4ed79b2d50ea03fd1817007e35062c9fe7a58e6cad025f3b24",
    ],
)

rpm(
    name = "libverto-libev-0__0.3.2-3.el9.x86_64",
    sha256 = "7d4423bc582773e23bf08f1f73d99275838a45fa188971a2f20448811e524a50",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libverto-libev-0.3.2-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7d4423bc582773e23bf08f1f73d99275838a45fa188971a2f20448811e524a50",
    ],
)

rpm(
    name = "libvirt-client-0__9.0.0-3.el9.aarch64",
    sha256 = "fd45fff545f0d4ae8b38371e80ca88982f5a7d0d29a52b7023fda602584e98a5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libvirt-client-9.0.0-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/fd45fff545f0d4ae8b38371e80ca88982f5a7d0d29a52b7023fda602584e98a5",
    ],
)

rpm(
    name = "libvirt-client-0__9.0.0-3.el9.x86_64",
    sha256 = "b1614274aa00dbe203339f2240c0175e92ea7a6ff5f7528e9c2e3fe1bd9795ed",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libvirt-client-9.0.0-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b1614274aa00dbe203339f2240c0175e92ea7a6ff5f7528e9c2e3fe1bd9795ed",
    ],
)

rpm(
    name = "libvirt-daemon-0__9.0.0-3.el9.aarch64",
    sha256 = "4af1dedef86620b3259bd6bd20433be8b62c672c85923fd3d2010c3a528cf84c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libvirt-daemon-9.0.0-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4af1dedef86620b3259bd6bd20433be8b62c672c85923fd3d2010c3a528cf84c",
    ],
)

rpm(
    name = "libvirt-daemon-0__9.0.0-3.el9.x86_64",
    sha256 = "507cb331253b707e8b44928551efa7e1ca94b799a68fd8c2326e26e5e68b5ff3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libvirt-daemon-9.0.0-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/507cb331253b707e8b44928551efa7e1ca94b799a68fd8c2326e26e5e68b5ff3",
    ],
)

rpm(
    name = "libvirt-daemon-driver-qemu-0__9.0.0-3.el9.aarch64",
    sha256 = "85293b52abfab72b8526d99433f92155d96ab8933a35fa4bc0fe0f76fdfb6b9a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libvirt-daemon-driver-qemu-9.0.0-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/85293b52abfab72b8526d99433f92155d96ab8933a35fa4bc0fe0f76fdfb6b9a",
    ],
)

rpm(
    name = "libvirt-daemon-driver-qemu-0__9.0.0-3.el9.x86_64",
    sha256 = "bfe1b7a1eed962ee3eae2614c13528328dfc8b2539abbdcae6c7eaf6f99e7328",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libvirt-daemon-driver-qemu-9.0.0-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/bfe1b7a1eed962ee3eae2614c13528328dfc8b2539abbdcae6c7eaf6f99e7328",
    ],
)

rpm(
    name = "libvirt-daemon-driver-secret-0__9.0.0-3.el9.x86_64",
    sha256 = "0b74b80a2237f7a1a9b058d9f754a73583c0515d4cfe788c0d37083c81be6f4f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libvirt-daemon-driver-secret-9.0.0-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/0b74b80a2237f7a1a9b058d9f754a73583c0515d4cfe788c0d37083c81be6f4f",
    ],
)

rpm(
    name = "libvirt-daemon-driver-storage-core-0__9.0.0-3.el9.x86_64",
    sha256 = "6bca33109eff6c8153e01de0075d5aa77c71af24abc1fc556e89439e8736ec75",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libvirt-daemon-driver-storage-core-9.0.0-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/6bca33109eff6c8153e01de0075d5aa77c71af24abc1fc556e89439e8736ec75",
    ],
)

rpm(
    name = "libvirt-devel-0__9.0.0-3.el9.aarch64",
    sha256 = "b6fad246120df16d27eb11640c0025d9ae5e821b3848233018856dd3e47b93ad",
    urls = [
        "http://mirror.stream.centos.org/9-stream/CRB/aarch64/os/Packages/libvirt-devel-9.0.0-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/b6fad246120df16d27eb11640c0025d9ae5e821b3848233018856dd3e47b93ad",
    ],
)

rpm(
    name = "libvirt-devel-0__9.0.0-3.el9.x86_64",
    sha256 = "25bfbba74e6d74753e7e66730c9e8e691f8465172ddf0d0ca7e42f79674e73ae",
    urls = [
        "http://mirror.stream.centos.org/9-stream/CRB/x86_64/os/Packages/libvirt-devel-9.0.0-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/25bfbba74e6d74753e7e66730c9e8e691f8465172ddf0d0ca7e42f79674e73ae",
    ],
)

rpm(
    name = "libvirt-libs-0__9.0.0-3.el9.aarch64",
    sha256 = "23d9ffd8dfc4742b7211029bda9ea6d527bf0cf174d561ea8945e5caeb4e9290",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libvirt-libs-9.0.0-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/23d9ffd8dfc4742b7211029bda9ea6d527bf0cf174d561ea8945e5caeb4e9290",
    ],
)

rpm(
    name = "libvirt-libs-0__9.0.0-3.el9.x86_64",
    sha256 = "08afbfa45dd08729533e366901ce82cccc98c5738088a335245d1ea363d5a076",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libvirt-libs-9.0.0-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/08afbfa45dd08729533e366901ce82cccc98c5738088a335245d1ea363d5a076",
    ],
)

rpm(
    name = "libxcrypt-0__4.4.18-3.el9.aarch64",
    sha256 = "f697d91abb19e9be9b69b8836a802711d2cf7989af27a4e1ba261f35ce53b8b5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libxcrypt-4.4.18-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/f697d91abb19e9be9b69b8836a802711d2cf7989af27a4e1ba261f35ce53b8b5",
    ],
)

rpm(
    name = "libxcrypt-0__4.4.18-3.el9.x86_64",
    sha256 = "97e88678b420f619a44608fff30062086aa1dd6931ecbd54f21bba005ff1de1a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libxcrypt-4.4.18-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/97e88678b420f619a44608fff30062086aa1dd6931ecbd54f21bba005ff1de1a",
    ],
)

rpm(
    name = "libxcrypt-devel-0__4.4.18-3.el9.aarch64",
    sha256 = "4d6085cd4068264576d023784ceddf0d9e19eb7633d87c31efd9444dab0c3420",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/libxcrypt-devel-4.4.18-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4d6085cd4068264576d023784ceddf0d9e19eb7633d87c31efd9444dab0c3420",
    ],
)

rpm(
    name = "libxcrypt-devel-0__4.4.18-3.el9.x86_64",
    sha256 = "162461e5f31f94907c91815370b545844cc9d33b1311e0063e23ae427241d1e0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/libxcrypt-devel-4.4.18-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/162461e5f31f94907c91815370b545844cc9d33b1311e0063e23ae427241d1e0",
    ],
)

rpm(
    name = "libxcrypt-static-0__4.4.18-3.el9.aarch64",
    sha256 = "34033b8a089eac80956a9542a77b4c5e8c32a27ab0e8cf61728a9fbac970d5ad",
    urls = [
        "http://mirror.stream.centos.org/9-stream/CRB/aarch64/os/Packages/libxcrypt-static-4.4.18-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/34033b8a089eac80956a9542a77b4c5e8c32a27ab0e8cf61728a9fbac970d5ad",
    ],
)

rpm(
    name = "libxcrypt-static-0__4.4.18-3.el9.x86_64",
    sha256 = "251a45a42a342459303bb1b928359eed1ea88bcd12605a9fe084f24fac020869",
    urls = [
        "http://mirror.stream.centos.org/9-stream/CRB/x86_64/os/Packages/libxcrypt-static-4.4.18-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/251a45a42a342459303bb1b928359eed1ea88bcd12605a9fe084f24fac020869",
    ],
)

rpm(
    name = "libxml2-0__2.9.13-3.el9.aarch64",
    sha256 = "6ece5c6a02ba54855bf0a1839021e8b06439c21b025f11b6d2f4191dd65103bb",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libxml2-2.9.13-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/6ece5c6a02ba54855bf0a1839021e8b06439c21b025f11b6d2f4191dd65103bb",
    ],
)

rpm(
    name = "libxml2-0__2.9.13-3.el9.x86_64",
    sha256 = "fb8e9a41956d07af0749b921e8c625311877b3257430d149e1903bcd16899f41",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libxml2-2.9.13-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fb8e9a41956d07af0749b921e8c625311877b3257430d149e1903bcd16899f41",
    ],
)

rpm(
    name = "libzstd-0__1.5.1-2.el9.aarch64",
    sha256 = "68101e014106305c840611b64d71311600edb30a34e09514c169c9eef6090d42",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/libzstd-1.5.1-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/68101e014106305c840611b64d71311600edb30a34e09514c169c9eef6090d42",
    ],
)

rpm(
    name = "libzstd-0__1.5.1-2.el9.x86_64",
    sha256 = "0840678cb3c1b418286f55da6973df9468c4cf500192de82d05ef28e6b4215a0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/libzstd-1.5.1-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/0840678cb3c1b418286f55da6973df9468c4cf500192de82d05ef28e6b4215a0",
    ],
)

rpm(
    name = "lua-libs-0__5.4.4-3.el9.aarch64",
    sha256 = "19dfb6fae113418ace8089e1462339afa4f318d91b219f0626a50b8213e44055",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/lua-libs-5.4.4-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/19dfb6fae113418ace8089e1462339afa4f318d91b219f0626a50b8213e44055",
    ],
)

rpm(
    name = "lua-libs-0__5.4.4-3.el9.x86_64",
    sha256 = "e5c66e676a4beff4a612275abff12a810dd8c00b2b9e731e1310876f1e35365c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/lua-libs-5.4.4-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/e5c66e676a4beff4a612275abff12a810dd8c00b2b9e731e1310876f1e35365c",
    ],
)

rpm(
    name = "lz4-libs-0__1.9.3-5.el9.aarch64",
    sha256 = "9aa14d26393dd46c0a390cf04f939f7f759a33165bdb506f8bee0653f3b70f45",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/lz4-libs-1.9.3-5.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/9aa14d26393dd46c0a390cf04f939f7f759a33165bdb506f8bee0653f3b70f45",
    ],
)

rpm(
    name = "lz4-libs-0__1.9.3-5.el9.x86_64",
    sha256 = "cba6a63054d070956a182e33269ee245bcfbe87e3e605c27816519db762a66ad",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/lz4-libs-1.9.3-5.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/cba6a63054d070956a182e33269ee245bcfbe87e3e605c27816519db762a66ad",
    ],
)

rpm(
    name = "lzo-0__2.10-7.el9.aarch64",
    sha256 = "eb10493cb600631bc42b0c0bad707f9b79da912750fa9b9e5d8a9978a98babdf",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/lzo-2.10-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/eb10493cb600631bc42b0c0bad707f9b79da912750fa9b9e5d8a9978a98babdf",
    ],
)

rpm(
    name = "lzo-0__2.10-7.el9.x86_64",
    sha256 = "7bee77c82bd6c183bba7a4b4fdd3ecb99d0a089a25c735ebbabc44e0c51e4b2e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/lzo-2.10-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7bee77c82bd6c183bba7a4b4fdd3ecb99d0a089a25c735ebbabc44e0c51e4b2e",
    ],
)

rpm(
    name = "lzop-0__1.04-8.el9.aarch64",
    sha256 = "ae5bdeee08c76f6ce902c70e16b373160e1c595dd1718f2f1db3a37ec5d63703",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/lzop-1.04-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/ae5bdeee08c76f6ce902c70e16b373160e1c595dd1718f2f1db3a37ec5d63703",
    ],
)

rpm(
    name = "lzop-0__1.04-8.el9.x86_64",
    sha256 = "ad84787d14a62195822ea89cec0fcf475f09b425f0822ce34d858d2d8bbd9466",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/lzop-1.04-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/ad84787d14a62195822ea89cec0fcf475f09b425f0822ce34d858d2d8bbd9466",
    ],
)

rpm(
    name = "make-1__4.3-7.el9.aarch64",
    sha256 = "63386f5e0f71bfff56bc73906e70e0a3a9d6679f5e272381a7b1f954d2a27367",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/make-4.3-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/63386f5e0f71bfff56bc73906e70e0a3a9d6679f5e272381a7b1f954d2a27367",
    ],
)

rpm(
    name = "make-1__4.3-7.el9.x86_64",
    sha256 = "d2c768e50950964bfdcefb9f1a36b268ae695fdea2bfd24daf8587def885e55d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/make-4.3-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d2c768e50950964bfdcefb9f1a36b268ae695fdea2bfd24daf8587def885e55d",
    ],
)

rpm(
    name = "mpfr-0__4.1.0-7.el9.aarch64",
    sha256 = "f3bd8510505a53450abe05dc34edbc5313fe89a6f88d0252624205dc7bb884c7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/mpfr-4.1.0-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/f3bd8510505a53450abe05dc34edbc5313fe89a6f88d0252624205dc7bb884c7",
    ],
)

rpm(
    name = "mpfr-0__4.1.0-7.el9.x86_64",
    sha256 = "179760104aa5a31ca463c586d0f21f380ba4d0eed212eee91bd1ca513e5d7a8d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/mpfr-4.1.0-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/179760104aa5a31ca463c586d0f21f380ba4d0eed212eee91bd1ca513e5d7a8d",
    ],
)

rpm(
    name = "ncurses-base-0__6.2-8.20210508.el9.aarch64",
    sha256 = "e4cc4a4a479b8c27776debba5c20e8ef21dc4b513da62a25ed09f88386ac08a8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/ncurses-base-6.2-8.20210508.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/e4cc4a4a479b8c27776debba5c20e8ef21dc4b513da62a25ed09f88386ac08a8",
    ],
)

rpm(
    name = "ncurses-base-0__6.2-8.20210508.el9.x86_64",
    sha256 = "e4cc4a4a479b8c27776debba5c20e8ef21dc4b513da62a25ed09f88386ac08a8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/ncurses-base-6.2-8.20210508.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/e4cc4a4a479b8c27776debba5c20e8ef21dc4b513da62a25ed09f88386ac08a8",
    ],
)

rpm(
    name = "ncurses-libs-0__6.2-8.20210508.el9.aarch64",
    sha256 = "26a21395b0bb4f7b60ab89bacaa8fc210c9921f1aba90ec950b91b3ee9e25dcc",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/ncurses-libs-6.2-8.20210508.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/26a21395b0bb4f7b60ab89bacaa8fc210c9921f1aba90ec950b91b3ee9e25dcc",
    ],
)

rpm(
    name = "ncurses-libs-0__6.2-8.20210508.el9.x86_64",
    sha256 = "328f4d50e66b00f24344ebe239817204fda8e68b1d988c6943abb3c36231beaa",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/ncurses-libs-6.2-8.20210508.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/328f4d50e66b00f24344ebe239817204fda8e68b1d988c6943abb3c36231beaa",
    ],
)

rpm(
    name = "ndctl-libs-0__71.1-8.el9.x86_64",
    sha256 = "69d469e5106559ca5a156a2191f85e89fd44f7866701bfb35e197e5133413098",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/ndctl-libs-71.1-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/69d469e5106559ca5a156a2191f85e89fd44f7866701bfb35e197e5133413098",
    ],
)

rpm(
    name = "nettle-0__3.8-3.el9.aarch64",
    sha256 = "94386170c99bb195481806f20ae034f246e863fc02a1eeaddf88212ae545f826",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/nettle-3.8-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/94386170c99bb195481806f20ae034f246e863fc02a1eeaddf88212ae545f826",
    ],
)

rpm(
    name = "nettle-0__3.8-3.el9.x86_64",
    sha256 = "ed956f9e018ab00d6ddf567487dd6bbcdc634d27dd69b485b416c6cf40026b82",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/nettle-3.8-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/ed956f9e018ab00d6ddf567487dd6bbcdc634d27dd69b485b416c6cf40026b82",
    ],
)

rpm(
    name = "nfs-utils-1__2.5.4-18.el9.x86_64",
    sha256 = "8d15e3b1003930dbf1b6ad3ebf4f77833e864ce50d051bc007c1ce03782b1d1f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/nfs-utils-2.5.4-18.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/8d15e3b1003930dbf1b6ad3ebf4f77833e864ce50d051bc007c1ce03782b1d1f",
    ],
)

rpm(
    name = "nftables-1__1.0.4-10.el9.aarch64",
    sha256 = "03f20f6478763b1e4691d946929110da8571f6cc07c6977ff5234f382cc19698",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/nftables-1.0.4-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/03f20f6478763b1e4691d946929110da8571f6cc07c6977ff5234f382cc19698",
    ],
)

rpm(
    name = "nftables-1__1.0.4-10.el9.x86_64",
    sha256 = "94a1828fabb047dacfc637f73831b7d2f2a2ff82984984c4af125f5efe0f2329",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/nftables-1.0.4-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/94a1828fabb047dacfc637f73831b7d2f2a2ff82984984c4af125f5efe0f2329",
    ],
)

rpm(
    name = "nmap-ncat-3__7.92-1.el9.aarch64",
    sha256 = "521d708d7679c793d5fc63d7c51800bfaf39090d36f9eebee63cbf874f2c993f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/nmap-ncat-7.92-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/521d708d7679c793d5fc63d7c51800bfaf39090d36f9eebee63cbf874f2c993f",
    ],
)

rpm(
    name = "nmap-ncat-3__7.92-1.el9.x86_64",
    sha256 = "59e5378a2a0188793559e27feb1cdf66f195c3b3e1280b5b182a66d7c3803962",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/nmap-ncat-7.92-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/59e5378a2a0188793559e27feb1cdf66f195c3b3e1280b5b182a66d7c3803962",
    ],
)

rpm(
    name = "npth-0__1.6-8.el9.x86_64",
    sha256 = "a7da4ef003bc60045bc60dae299b703e7f1db326f25208fb922ce1b79e2882da",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/npth-1.6-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/a7da4ef003bc60045bc60dae299b703e7f1db326f25208fb922ce1b79e2882da",
    ],
)

rpm(
    name = "numactl-libs-0__2.0.14-7.el9.aarch64",
    sha256 = "288250e514a6d1e4299656c1b68d49653cc92060a35024631c80fc0f206cf433",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/numactl-libs-2.0.14-7.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/288250e514a6d1e4299656c1b68d49653cc92060a35024631c80fc0f206cf433",
    ],
)

rpm(
    name = "numactl-libs-0__2.0.14-7.el9.x86_64",
    sha256 = "7a3bc16b3fee48c53e0f54a7cb4cd3857eb1be3984d58da3bdf2c297d6b55af1",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/numactl-libs-2.0.14-7.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7a3bc16b3fee48c53e0f54a7cb4cd3857eb1be3984d58da3bdf2c297d6b55af1",
    ],
)

rpm(
    name = "numad-0__0.5-36.20150602git.el9.aarch64",
    sha256 = "c7cd5aa2f682cfa56f9c35f4c0b28a2e75c23dee993b54e4c39c21931392f6bb",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/numad-0.5-36.20150602git.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/c7cd5aa2f682cfa56f9c35f4c0b28a2e75c23dee993b54e4c39c21931392f6bb",
    ],
)

rpm(
    name = "numad-0__0.5-36.20150602git.el9.x86_64",
    sha256 = "1b4242cdefa165b70926aee4dd4606b0f5ecdf4a436812746e9fe1c417724d23",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/numad-0.5-36.20150602git.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/1b4242cdefa165b70926aee4dd4606b0f5ecdf4a436812746e9fe1c417724d23",
    ],
)

rpm(
    name = "openldap-0__2.6.2-3.el9.aarch64",
    sha256 = "492daf98d77aa62021d3956e0a0727c66bd13c2322267c8e6556bfbb68c06fa5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/openldap-2.6.2-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/492daf98d77aa62021d3956e0a0727c66bd13c2322267c8e6556bfbb68c06fa5",
    ],
)

rpm(
    name = "openldap-0__2.6.2-3.el9.x86_64",
    sha256 = "8ce2a645dfc4444c698d8c2a644df93fd53b9a00ef887e138528aa473ee76456",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/openldap-2.6.2-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/8ce2a645dfc4444c698d8c2a644df93fd53b9a00ef887e138528aa473ee76456",
    ],
)

rpm(
    name = "openssl-1__3.0.7-6.el9.aarch64",
    sha256 = "4afdee6ee63e7da44069fd00a8d8f5ab3779cb22f157f3dcc9c47eeac40978ff",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/openssl-3.0.7-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4afdee6ee63e7da44069fd00a8d8f5ab3779cb22f157f3dcc9c47eeac40978ff",
    ],
)

rpm(
    name = "openssl-1__3.0.7-6.el9.x86_64",
    sha256 = "652b1eefef3578e18a66f1feab36988cb7b1e339fb0d9f023c502a307da6cf15",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/openssl-3.0.7-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/652b1eefef3578e18a66f1feab36988cb7b1e339fb0d9f023c502a307da6cf15",
    ],
)

rpm(
    name = "openssl-libs-1__3.0.7-6.el9.aarch64",
    sha256 = "bc9a18f03ea617f894c4fa9290676958ebfdd29d1ce67a0619ad6922114524dc",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/openssl-libs-3.0.7-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/bc9a18f03ea617f894c4fa9290676958ebfdd29d1ce67a0619ad6922114524dc",
    ],
)

rpm(
    name = "openssl-libs-1__3.0.7-6.el9.x86_64",
    sha256 = "88da5da36af38544c7f498f076a4afba212fd6b700ce2fb96d7978c2b8d82d85",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/openssl-libs-3.0.7-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/88da5da36af38544c7f498f076a4afba212fd6b700ce2fb96d7978c2b8d82d85",
    ],
)

rpm(
    name = "p11-kit-0__0.24.1-2.el9.aarch64",
    sha256 = "98e7f00d012549fa8fbaba21626388a0b07731f3f25a5801418247d66a5a985f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/p11-kit-0.24.1-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/98e7f00d012549fa8fbaba21626388a0b07731f3f25a5801418247d66a5a985f",
    ],
)

rpm(
    name = "p11-kit-0__0.24.1-2.el9.x86_64",
    sha256 = "da167e41efd19cf25fd1c708b6f123d0203824324b14dd32401d49f2aa0ef0a6",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/p11-kit-0.24.1-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/da167e41efd19cf25fd1c708b6f123d0203824324b14dd32401d49f2aa0ef0a6",
    ],
)

rpm(
    name = "p11-kit-trust-0__0.24.1-2.el9.aarch64",
    sha256 = "80e288a5b62f20f7794674c6fdf2f0765a322cd0e81df9359e37582fe950289c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/p11-kit-trust-0.24.1-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/80e288a5b62f20f7794674c6fdf2f0765a322cd0e81df9359e37582fe950289c",
    ],
)

rpm(
    name = "p11-kit-trust-0__0.24.1-2.el9.x86_64",
    sha256 = "ae9a633c58980328bef6358c6aa3c9ce0a65130c66fbfa4249922ddf5a3e2bb1",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/p11-kit-trust-0.24.1-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/ae9a633c58980328bef6358c6aa3c9ce0a65130c66fbfa4249922ddf5a3e2bb1",
    ],
)

rpm(
    name = "pam-0__1.5.1-14.el9.aarch64",
    sha256 = "130625dc257f6d0da5e4b523b191370613100f0c00cfb681192bf5955c100d8f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/pam-1.5.1-14.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/130625dc257f6d0da5e4b523b191370613100f0c00cfb681192bf5955c100d8f",
    ],
)

rpm(
    name = "pam-0__1.5.1-14.el9.x86_64",
    sha256 = "c4d8be2502028e700815c3c80a9cd4c23618ae70a6b9af27a9996c1f9b3b93c8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/pam-1.5.1-14.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c4d8be2502028e700815c3c80a9cd4c23618ae70a6b9af27a9996c1f9b3b93c8",
    ],
)

rpm(
    name = "parted-0__3.5-2.el9.x86_64",
    sha256 = "ab6500203b5f0b3bd551c026ca60e5aec51170bdc62978a2702d386d2a645b5e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/parted-3.5-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/ab6500203b5f0b3bd551c026ca60e5aec51170bdc62978a2702d386d2a645b5e",
    ],
)

rpm(
    name = "passt-0__0__caret__20221110.g4129764-1.el9.aarch64",
    sha256 = "61b885cbe37e2204ac49226541c10fec3be4efe6d10cd707b416bbdd1a6231da",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/passt-0%5E20221110.g4129764-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/61b885cbe37e2204ac49226541c10fec3be4efe6d10cd707b416bbdd1a6231da",
    ],
)

rpm(
    name = "passt-0__0__caret__20221110.g4129764-1.el9.x86_64",
    sha256 = "fa2f8e30695df5254f75855ef8e32163d0350ca23f549e41284f1f6b90ae029d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/passt-0%5E20221110.g4129764-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/fa2f8e30695df5254f75855ef8e32163d0350ca23f549e41284f1f6b90ae029d",
    ],
)

rpm(
    name = "pcre-0__8.44-3.el9.3.aarch64",
    sha256 = "0331efd537704e75e26324ba6bb1568762d01bafe7fbce5b981ff0ee0d3ea80c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/pcre-8.44-3.el9.3.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/0331efd537704e75e26324ba6bb1568762d01bafe7fbce5b981ff0ee0d3ea80c",
    ],
)

rpm(
    name = "pcre-0__8.44-3.el9.3.x86_64",
    sha256 = "4a3cb61eb08c4f24e44756b6cb329812fe48d5c65c1fba546fadfa975045a8c5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/pcre-8.44-3.el9.3.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/4a3cb61eb08c4f24e44756b6cb329812fe48d5c65c1fba546fadfa975045a8c5",
    ],
)

rpm(
    name = "pcre2-0__10.40-2.el9.aarch64",
    sha256 = "8879da4bf6f8ec1a17105a3d54130d77afad48021c7280d8edb3f63fed80c4a5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/pcre2-10.40-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/8879da4bf6f8ec1a17105a3d54130d77afad48021c7280d8edb3f63fed80c4a5",
    ],
)

rpm(
    name = "pcre2-0__10.40-2.el9.x86_64",
    sha256 = "8cc83f9f130e6ef50d54d75eb4050ce879d8acaf5bb616b398ad92c1ad2b3d21",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/pcre2-10.40-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/8cc83f9f130e6ef50d54d75eb4050ce879d8acaf5bb616b398ad92c1ad2b3d21",
    ],
)

rpm(
    name = "pcre2-syntax-0__10.40-2.el9.aarch64",
    sha256 = "4dad144194fe6794c7621c38b6a7f917a81ceaeb3f2be25833b9b0af1181ebe2",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/pcre2-syntax-10.40-2.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/4dad144194fe6794c7621c38b6a7f917a81ceaeb3f2be25833b9b0af1181ebe2",
    ],
)

rpm(
    name = "pcre2-syntax-0__10.40-2.el9.x86_64",
    sha256 = "4dad144194fe6794c7621c38b6a7f917a81ceaeb3f2be25833b9b0af1181ebe2",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/pcre2-syntax-10.40-2.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/4dad144194fe6794c7621c38b6a7f917a81ceaeb3f2be25833b9b0af1181ebe2",
    ],
)

rpm(
    name = "pixman-0__0.40.0-5.el9.aarch64",
    sha256 = "0cb4f93b6307d5c1cbc6738b187eaac08ce571297fb4a0bd0f8f2a9c843db83b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/pixman-0.40.0-5.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/0cb4f93b6307d5c1cbc6738b187eaac08ce571297fb4a0bd0f8f2a9c843db83b",
    ],
)

rpm(
    name = "pixman-0__0.40.0-5.el9.x86_64",
    sha256 = "8673872772fec90180fa9688363b4d808c5d01bd9951afaddfa7e64bb7274aba",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/pixman-0.40.0-5.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/8673872772fec90180fa9688363b4d808c5d01bd9951afaddfa7e64bb7274aba",
    ],
)

rpm(
    name = "pkgconf-0__1.7.3-10.el9.aarch64",
    sha256 = "94f174c9829d44f345bb8a734147f379ba95fb47d04befdb20a17e8b158b3710",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/pkgconf-1.7.3-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/94f174c9829d44f345bb8a734147f379ba95fb47d04befdb20a17e8b158b3710",
    ],
)

rpm(
    name = "pkgconf-0__1.7.3-10.el9.x86_64",
    sha256 = "2ff8b131570687e4eca9877feaa9058ef7c0772cff507c019f6c26aff126d065",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/pkgconf-1.7.3-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/2ff8b131570687e4eca9877feaa9058ef7c0772cff507c019f6c26aff126d065",
    ],
)

rpm(
    name = "pkgconf-m4-0__1.7.3-10.el9.aarch64",
    sha256 = "de4946454f110a9b12ab50c9c3dfaa68633b4ae3cb4e5278b23d491eb3edc27a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/pkgconf-m4-1.7.3-10.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/de4946454f110a9b12ab50c9c3dfaa68633b4ae3cb4e5278b23d491eb3edc27a",
    ],
)

rpm(
    name = "pkgconf-m4-0__1.7.3-10.el9.x86_64",
    sha256 = "de4946454f110a9b12ab50c9c3dfaa68633b4ae3cb4e5278b23d491eb3edc27a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/pkgconf-m4-1.7.3-10.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/de4946454f110a9b12ab50c9c3dfaa68633b4ae3cb4e5278b23d491eb3edc27a",
    ],
)

rpm(
    name = "pkgconf-pkg-config-0__1.7.3-10.el9.aarch64",
    sha256 = "d36ff5361c4b31273b15ff34f0fec5ae5316d6555270b3d051d97c85c12defac",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/pkgconf-pkg-config-1.7.3-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/d36ff5361c4b31273b15ff34f0fec5ae5316d6555270b3d051d97c85c12defac",
    ],
)

rpm(
    name = "pkgconf-pkg-config-0__1.7.3-10.el9.x86_64",
    sha256 = "e308e84f06756bf3c14bc426fb2519008ad8423925c4662bb379ea87aced19d9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/pkgconf-pkg-config-1.7.3-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/e308e84f06756bf3c14bc426fb2519008ad8423925c4662bb379ea87aced19d9",
    ],
)

rpm(
    name = "policycoreutils-0__3.5-1.el9.aarch64",
    sha256 = "90c11486bc67102dbe1d48f7e03f9f831e7aca161cd1b873e5521bef0f8e1652",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/policycoreutils-3.5-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/90c11486bc67102dbe1d48f7e03f9f831e7aca161cd1b873e5521bef0f8e1652",
    ],
)

rpm(
    name = "policycoreutils-0__3.5-1.el9.x86_64",
    sha256 = "3d58010e9b0de6e76f33f94624973635f574478b45ea90711f598fd3c778e6b7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/policycoreutils-3.5-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/3d58010e9b0de6e76f33f94624973635f574478b45ea90711f598fd3c778e6b7",
    ],
)

rpm(
    name = "polkit-0__0.117-11.el9.aarch64",
    sha256 = "89396fbd7ee82b5e275b4710e97c66a82e6f8ea3f06801583255c5afb4fbb1a7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/polkit-0.117-11.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/89396fbd7ee82b5e275b4710e97c66a82e6f8ea3f06801583255c5afb4fbb1a7",
    ],
)

rpm(
    name = "polkit-0__0.117-11.el9.x86_64",
    sha256 = "aa1dba30bfe853f39cb75bb83de6b4aebf81bed3b743b29ca325558320834b0d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/polkit-0.117-11.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/aa1dba30bfe853f39cb75bb83de6b4aebf81bed3b743b29ca325558320834b0d",
    ],
)

rpm(
    name = "polkit-libs-0__0.117-11.el9.aarch64",
    sha256 = "80b4bec3572e4be6c17deab334b45b31667b00fec587b339607239429c67b278",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/polkit-libs-0.117-11.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/80b4bec3572e4be6c17deab334b45b31667b00fec587b339607239429c67b278",
    ],
)

rpm(
    name = "polkit-libs-0__0.117-11.el9.x86_64",
    sha256 = "975049fa240c818d49dfc22716e270de7c193fe526f93f091fc0f91f361921d8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/polkit-libs-0.117-11.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/975049fa240c818d49dfc22716e270de7c193fe526f93f091fc0f91f361921d8",
    ],
)

rpm(
    name = "polkit-pkla-compat-0__0.1-21.el9.aarch64",
    sha256 = "c22bfa6ebfb7c8803cd115e750f29408a00d73475ec8b77d409b7eabd2aeb61a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/polkit-pkla-compat-0.1-21.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/c22bfa6ebfb7c8803cd115e750f29408a00d73475ec8b77d409b7eabd2aeb61a",
    ],
)

rpm(
    name = "polkit-pkla-compat-0__0.1-21.el9.x86_64",
    sha256 = "ffb4cc04548f24cf7cd62da9747d3839af7676b29b60cfd3da59c6ec31ebdf99",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/polkit-pkla-compat-0.1-21.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/ffb4cc04548f24cf7cd62da9747d3839af7676b29b60cfd3da59c6ec31ebdf99",
    ],
)

rpm(
    name = "popt-0__1.18-8.el9.aarch64",
    sha256 = "032427adaa37d2a1c6d2f3cab42ccbdce2c6d9b3c1f3cd91c05a92c99198babb",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/popt-1.18-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/032427adaa37d2a1c6d2f3cab42ccbdce2c6d9b3c1f3cd91c05a92c99198babb",
    ],
)

rpm(
    name = "popt-0__1.18-8.el9.x86_64",
    sha256 = "d864419035e99f8bb06f5d1c767608ed81f942cb128a98b590c1dbc4afbd54d4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/popt-1.18-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d864419035e99f8bb06f5d1c767608ed81f942cb128a98b590c1dbc4afbd54d4",
    ],
)

rpm(
    name = "procps-ng-0__3.3.17-11.el9.aarch64",
    sha256 = "3c1a68384fb8b4427012670ef3cad1353bc99cb2f28371776faab80522996655",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/procps-ng-3.3.17-11.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/3c1a68384fb8b4427012670ef3cad1353bc99cb2f28371776faab80522996655",
    ],
)

rpm(
    name = "procps-ng-0__3.3.17-11.el9.x86_64",
    sha256 = "f808260d770cd060a8640f962329502982006c6614373651c628b1fcc17bf5bd",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/procps-ng-3.3.17-11.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/f808260d770cd060a8640f962329502982006c6614373651c628b1fcc17bf5bd",
    ],
)

rpm(
    name = "protobuf-c-0__1.3.3-12.el9.aarch64",
    sha256 = "f6096a23837dcf6755968c54d9a16875f3e9a86388f936ab1e2ff28e381f3cfa",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/protobuf-c-1.3.3-12.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/f6096a23837dcf6755968c54d9a16875f3e9a86388f936ab1e2ff28e381f3cfa",
    ],
)

rpm(
    name = "protobuf-c-0__1.3.3-12.el9.x86_64",
    sha256 = "5d1091426fc81321e00c805fff53b2da159de91d6d219d20f3defdfde41bf1d4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/protobuf-c-1.3.3-12.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/5d1091426fc81321e00c805fff53b2da159de91d6d219d20f3defdfde41bf1d4",
    ],
)

rpm(
    name = "psmisc-0__23.4-3.el9.aarch64",
    sha256 = "4ad245b41ebf13cbabbb2962fad8d4aa0db7c75eb2171a4235252ad48e81a680",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/psmisc-23.4-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4ad245b41ebf13cbabbb2962fad8d4aa0db7c75eb2171a4235252ad48e81a680",
    ],
)

rpm(
    name = "psmisc-0__23.4-3.el9.x86_64",
    sha256 = "e02fc28d42912689b006fcc1e98bdb5b0eefba538eb024c4e00ec9adc348449d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/psmisc-23.4-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/e02fc28d42912689b006fcc1e98bdb5b0eefba538eb024c4e00ec9adc348449d",
    ],
)

rpm(
    name = "python3-0__3.9.16-1.el9.aarch64",
    sha256 = "2e1684a706a883055425858bfc56cbf79e986c6123ca8b8206294b07f8e2fae4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-3.9.16-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/2e1684a706a883055425858bfc56cbf79e986c6123ca8b8206294b07f8e2fae4",
    ],
)

rpm(
    name = "python3-0__3.9.16-1.el9.x86_64",
    sha256 = "7f21e3ee6bc5eaf4a8844440b277040e2df1a48f904afcc1c9943a2d059cee9e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-3.9.16-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7f21e3ee6bc5eaf4a8844440b277040e2df1a48f904afcc1c9943a2d059cee9e",
    ],
)

rpm(
    name = "python3-configshell-1__1.1.28-7.el9.aarch64",
    sha256 = "39d28be696eb7b915c2d0be2da6a4f98ed8888ad03acd5c30f863387adfc5386",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-configshell-1.1.28-7.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/39d28be696eb7b915c2d0be2da6a4f98ed8888ad03acd5c30f863387adfc5386",
    ],
)

rpm(
    name = "python3-configshell-1__1.1.28-7.el9.x86_64",
    sha256 = "39d28be696eb7b915c2d0be2da6a4f98ed8888ad03acd5c30f863387adfc5386",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-configshell-1.1.28-7.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/39d28be696eb7b915c2d0be2da6a4f98ed8888ad03acd5c30f863387adfc5386",
    ],
)

rpm(
    name = "python3-dbus-0__1.2.18-2.el9.aarch64",
    sha256 = "ce454fa8f9a2d015face9e9ae64f6730f2ba104d0556c91b93fca2006f132bf9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-dbus-1.2.18-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/ce454fa8f9a2d015face9e9ae64f6730f2ba104d0556c91b93fca2006f132bf9",
    ],
)

rpm(
    name = "python3-dbus-0__1.2.18-2.el9.x86_64",
    sha256 = "8e42f3e54292bfc76ab52ee3f91f850fb0cca63c9a49692938381ca93460a686",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-dbus-1.2.18-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/8e42f3e54292bfc76ab52ee3f91f850fb0cca63c9a49692938381ca93460a686",
    ],
)

rpm(
    name = "python3-gobject-base-0__3.40.1-6.el9.aarch64",
    sha256 = "815369710e8d7c6f7473380210283f9e6dfdc0c6cc553c4ea9cb709835937adb",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-gobject-base-3.40.1-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/815369710e8d7c6f7473380210283f9e6dfdc0c6cc553c4ea9cb709835937adb",
    ],
)

rpm(
    name = "python3-gobject-base-0__3.40.1-6.el9.x86_64",
    sha256 = "bb795c9ba439bd1a0329e3534001432c95c5c454ccc61029f68501006f539a51",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-gobject-base-3.40.1-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/bb795c9ba439bd1a0329e3534001432c95c5c454ccc61029f68501006f539a51",
    ],
)

rpm(
    name = "python3-gobject-base-noarch-0__3.40.1-6.el9.aarch64",
    sha256 = "57ae14f5296ed26cabd264a2b88a015b05f962b65c9633eb328da029a0372b01",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-gobject-base-noarch-3.40.1-6.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/57ae14f5296ed26cabd264a2b88a015b05f962b65c9633eb328da029a0372b01",
    ],
)

rpm(
    name = "python3-gobject-base-noarch-0__3.40.1-6.el9.x86_64",
    sha256 = "57ae14f5296ed26cabd264a2b88a015b05f962b65c9633eb328da029a0372b01",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-gobject-base-noarch-3.40.1-6.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/57ae14f5296ed26cabd264a2b88a015b05f962b65c9633eb328da029a0372b01",
    ],
)

rpm(
    name = "python3-kmod-0__0.9-32.el9.aarch64",
    sha256 = "600b42a5b139ea5f8b246561294581c09237d88ec9bbcce823f56213d7e2652f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-kmod-0.9-32.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/600b42a5b139ea5f8b246561294581c09237d88ec9bbcce823f56213d7e2652f",
    ],
)

rpm(
    name = "python3-kmod-0__0.9-32.el9.x86_64",
    sha256 = "e0b0ae0d507496349b667e0281b4d72ac3f7b7fa65c633c56afa3f328855a2d9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-kmod-0.9-32.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/e0b0ae0d507496349b667e0281b4d72ac3f7b7fa65c633c56afa3f328855a2d9",
    ],
)

rpm(
    name = "python3-libs-0__3.9.16-1.el9.aarch64",
    sha256 = "5b3ca2504a39b4d0a54fe0dccf8b3860156dbe56f6af7af2e6e9f58dc9301fe4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-libs-3.9.16-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/5b3ca2504a39b4d0a54fe0dccf8b3860156dbe56f6af7af2e6e9f58dc9301fe4",
    ],
)

rpm(
    name = "python3-libs-0__3.9.16-1.el9.x86_64",
    sha256 = "21a7fe05e3c1a36b8242f5c783f7cdf636634b69bbd21428089b948f9c2433bc",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-libs-3.9.16-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/21a7fe05e3c1a36b8242f5c783f7cdf636634b69bbd21428089b948f9c2433bc",
    ],
)

rpm(
    name = "python3-pip-wheel-0__21.2.3-6.el9.aarch64",
    sha256 = "8e9e72535944204b48dbcb9cb34007b4991bdb4b5223e4c5874b07c6c122c1ff",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-pip-wheel-21.2.3-6.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/8e9e72535944204b48dbcb9cb34007b4991bdb4b5223e4c5874b07c6c122c1ff",
    ],
)

rpm(
    name = "python3-pip-wheel-0__21.2.3-6.el9.x86_64",
    sha256 = "8e9e72535944204b48dbcb9cb34007b4991bdb4b5223e4c5874b07c6c122c1ff",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-pip-wheel-21.2.3-6.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/8e9e72535944204b48dbcb9cb34007b4991bdb4b5223e4c5874b07c6c122c1ff",
    ],
)

rpm(
    name = "python3-pyparsing-0__2.4.7-9.el9.aarch64",
    sha256 = "ee20a60fb835392fc76c1a1a3e9befa0e4b3d27bdcfbfb0aab90fcddf3c60439",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-pyparsing-2.4.7-9.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/ee20a60fb835392fc76c1a1a3e9befa0e4b3d27bdcfbfb0aab90fcddf3c60439",
    ],
)

rpm(
    name = "python3-pyparsing-0__2.4.7-9.el9.x86_64",
    sha256 = "ee20a60fb835392fc76c1a1a3e9befa0e4b3d27bdcfbfb0aab90fcddf3c60439",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-pyparsing-2.4.7-9.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/ee20a60fb835392fc76c1a1a3e9befa0e4b3d27bdcfbfb0aab90fcddf3c60439",
    ],
)

rpm(
    name = "python3-pyudev-0__0.22.0-6.el9.aarch64",
    sha256 = "db815d76afabb8dd7eca6ca5a5bf838304f82824c41e4f06b6d25b5eb63c65c6",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-pyudev-0.22.0-6.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/db815d76afabb8dd7eca6ca5a5bf838304f82824c41e4f06b6d25b5eb63c65c6",
    ],
)

rpm(
    name = "python3-pyudev-0__0.22.0-6.el9.x86_64",
    sha256 = "db815d76afabb8dd7eca6ca5a5bf838304f82824c41e4f06b6d25b5eb63c65c6",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-pyudev-0.22.0-6.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/db815d76afabb8dd7eca6ca5a5bf838304f82824c41e4f06b6d25b5eb63c65c6",
    ],
)

rpm(
    name = "python3-rtslib-0__2.1.75-1.el9.aarch64",
    sha256 = "ddeac3075ca78cb0c61a229aec9d534aa99b9a6bb2b242a39e28baf6ef4c2f64",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/python3-rtslib-2.1.75-1.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/ddeac3075ca78cb0c61a229aec9d534aa99b9a6bb2b242a39e28baf6ef4c2f64",
    ],
)

rpm(
    name = "python3-rtslib-0__2.1.75-1.el9.x86_64",
    sha256 = "ddeac3075ca78cb0c61a229aec9d534aa99b9a6bb2b242a39e28baf6ef4c2f64",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/python3-rtslib-2.1.75-1.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/ddeac3075ca78cb0c61a229aec9d534aa99b9a6bb2b242a39e28baf6ef4c2f64",
    ],
)

rpm(
    name = "python3-setuptools-wheel-0__53.0.0-12.el9.aarch64",
    sha256 = "de1a05afcb6087cf6fc6e38b952485239a72ae719538bd255e14789e606ab2ca",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-setuptools-wheel-53.0.0-12.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/de1a05afcb6087cf6fc6e38b952485239a72ae719538bd255e14789e606ab2ca",
    ],
)

rpm(
    name = "python3-setuptools-wheel-0__53.0.0-12.el9.x86_64",
    sha256 = "de1a05afcb6087cf6fc6e38b952485239a72ae719538bd255e14789e606ab2ca",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-setuptools-wheel-53.0.0-12.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/de1a05afcb6087cf6fc6e38b952485239a72ae719538bd255e14789e606ab2ca",
    ],
)

rpm(
    name = "python3-six-0__1.15.0-9.el9.aarch64",
    sha256 = "efecffed29602079a1ea1d41c819271ec705a97a68891b43e1d626b2fa0ea8a1",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-six-1.15.0-9.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/efecffed29602079a1ea1d41c819271ec705a97a68891b43e1d626b2fa0ea8a1",
    ],
)

rpm(
    name = "python3-six-0__1.15.0-9.el9.x86_64",
    sha256 = "efecffed29602079a1ea1d41c819271ec705a97a68891b43e1d626b2fa0ea8a1",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-six-1.15.0-9.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/efecffed29602079a1ea1d41c819271ec705a97a68891b43e1d626b2fa0ea8a1",
    ],
)

rpm(
    name = "python3-urwid-0__2.1.2-4.el9.aarch64",
    sha256 = "a91fcc1b5b01aeb0830d04f562cb843489f38d2606d8ab480a876207f4335990",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/python3-urwid-2.1.2-4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/a91fcc1b5b01aeb0830d04f562cb843489f38d2606d8ab480a876207f4335990",
    ],
)

rpm(
    name = "python3-urwid-0__2.1.2-4.el9.x86_64",
    sha256 = "b4e4915a49904035e0e8d8ed15a545f2d7191e9d760c438343980fbf0b66abf4",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/python3-urwid-2.1.2-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b4e4915a49904035e0e8d8ed15a545f2d7191e9d760c438343980fbf0b66abf4",
    ],
)

rpm(
    name = "qemu-img-17__7.2.0-14.el9.aarch64",
    sha256 = "7e0ecfdeb20e21b6bf74a4558bf32780bec21fb3f018ecbe69aabbd191ab2ab8",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/qemu-img-7.2.0-14.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/7e0ecfdeb20e21b6bf74a4558bf32780bec21fb3f018ecbe69aabbd191ab2ab8",
    ],
)

rpm(
    name = "qemu-img-17__7.2.0-14.el9.x86_64",
    sha256 = "01c0ef1facc0c117dbc46e1c5c6cc84f3db21b306db053226efdc23685090e35",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/qemu-img-7.2.0-14.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/01c0ef1facc0c117dbc46e1c5c6cc84f3db21b306db053226efdc23685090e35",
    ],
)

rpm(
    name = "qemu-kvm-common-17__7.2.0-14.el9.aarch64",
    sha256 = "c4d7302f3bc00bdaa380b0a82ab7611607ab1c7ee342cd01f61499c62fb002b2",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/qemu-kvm-common-7.2.0-14.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/c4d7302f3bc00bdaa380b0a82ab7611607ab1c7ee342cd01f61499c62fb002b2",
    ],
)

rpm(
    name = "qemu-kvm-common-17__7.2.0-14.el9.x86_64",
    sha256 = "4beacf105e014b552e36259994091611e78a3a92e753bef4d4ca93929c9714f9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/qemu-kvm-common-7.2.0-14.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/4beacf105e014b552e36259994091611e78a3a92e753bef4d4ca93929c9714f9",
    ],
)

rpm(
    name = "qemu-kvm-core-17__7.2.0-14.el9.aarch64",
    sha256 = "2254212d2d9af54cf8583126044b3cd3cc8118c5a8a576d982aede3b95fa903a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/qemu-kvm-core-7.2.0-14.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/2254212d2d9af54cf8583126044b3cd3cc8118c5a8a576d982aede3b95fa903a",
    ],
)

rpm(
    name = "qemu-kvm-core-17__7.2.0-14.el9.x86_64",
    sha256 = "163ea33de2979e0917e81839bf4c5e5ab8593c6c29668aac89bed70e689ba653",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/qemu-kvm-core-7.2.0-14.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/163ea33de2979e0917e81839bf4c5e5ab8593c6c29668aac89bed70e689ba653",
    ],
)

rpm(
    name = "qemu-kvm-device-display-virtio-gpu-17__7.2.0-14.el9.aarch64",
    sha256 = "a269855ea31f365617578c14f44ed9270336b10ec73c3df98965948512c81ef0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/qemu-kvm-device-display-virtio-gpu-7.2.0-14.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/a269855ea31f365617578c14f44ed9270336b10ec73c3df98965948512c81ef0",
    ],
)

rpm(
    name = "qemu-kvm-device-display-virtio-gpu-pci-17__7.2.0-14.el9.aarch64",
    sha256 = "761a0685466e82ec9213d6a0514fb8c5a4a56fcbbeacfcf91d0ce8664eedaedd",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/qemu-kvm-device-display-virtio-gpu-pci-7.2.0-14.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/761a0685466e82ec9213d6a0514fb8c5a4a56fcbbeacfcf91d0ce8664eedaedd",
    ],
)

rpm(
    name = "qemu-kvm-device-usb-redirect-17__7.2.0-14.el9.x86_64",
    sha256 = "b4072028518f3af376f578b49ecb1e8cc3f1104ad6749f818009728bf6f526ee",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/qemu-kvm-device-usb-redirect-7.2.0-14.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b4072028518f3af376f578b49ecb1e8cc3f1104ad6749f818009728bf6f526ee",
    ],
)

rpm(
    name = "qemu-pr-helper-17__7.2.0-14.el9.aarch64",
    sha256 = "c5b916ebbcd1a20b3eeaa512a93e2a3811ec69c6c80d93c0c57f86340114669e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/qemu-pr-helper-7.2.0-14.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/c5b916ebbcd1a20b3eeaa512a93e2a3811ec69c6c80d93c0c57f86340114669e",
    ],
)

rpm(
    name = "qemu-pr-helper-17__7.2.0-14.el9.x86_64",
    sha256 = "27556166b3a45a6ec324ef4df456670afb4e2700db0fb0cb4c82e0ae51cfc94c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/qemu-pr-helper-7.2.0-14.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/27556166b3a45a6ec324ef4df456670afb4e2700db0fb0cb4c82e0ae51cfc94c",
    ],
)

rpm(
    name = "quota-1__4.06-6.el9.x86_64",
    sha256 = "b4827d71208202beeecc6e661584b3cf008f2ee22ddd7250089dd94ff22be31e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/quota-4.06-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b4827d71208202beeecc6e661584b3cf008f2ee22ddd7250089dd94ff22be31e",
    ],
)

rpm(
    name = "quota-nls-1__4.06-6.el9.x86_64",
    sha256 = "7a63c4fcc7166563de95bfffb23b54db2b17c8cef178f5c0887ac8f5ab8ec1e3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/quota-nls-4.06-6.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/7a63c4fcc7166563de95bfffb23b54db2b17c8cef178f5c0887ac8f5ab8ec1e3",
    ],
)

rpm(
    name = "readline-0__8.1-4.el9.aarch64",
    sha256 = "2ecec47a882ff434cc869b691a7e1e8d7639bc1af44bcb214ff4921f675776aa",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/readline-8.1-4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/2ecec47a882ff434cc869b691a7e1e8d7639bc1af44bcb214ff4921f675776aa",
    ],
)

rpm(
    name = "readline-0__8.1-4.el9.x86_64",
    sha256 = "49945472925286ad89b0575657b43f9224777e36b442f0c88df67f0b61e26aee",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/readline-8.1-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/49945472925286ad89b0575657b43f9224777e36b442f0c88df67f0b61e26aee",
    ],
)

rpm(
    name = "rpcbind-0__1.2.6-5.el9.x86_64",
    sha256 = "9ff0aa1299bb78f3c494620283cd34bcc9a1aa9f03fc902f21ba4c4c854b1e22",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/rpcbind-1.2.6-5.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/9ff0aa1299bb78f3c494620283cd34bcc9a1aa9f03fc902f21ba4c4c854b1e22",
    ],
)

rpm(
    name = "rpm-0__4.16.1.3-22.el9.aarch64",
    sha256 = "111da55d1cf002b93dc586b54de8973594a085d47bb76ea248ea10cfdde32fb5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/rpm-4.16.1.3-22.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/111da55d1cf002b93dc586b54de8973594a085d47bb76ea248ea10cfdde32fb5",
    ],
)

rpm(
    name = "rpm-0__4.16.1.3-22.el9.x86_64",
    sha256 = "8d98bb7173e5135c776ba9e02be2beec9b73f44d3a5eae04db1046a2a8c1ef90",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/rpm-4.16.1.3-22.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/8d98bb7173e5135c776ba9e02be2beec9b73f44d3a5eae04db1046a2a8c1ef90",
    ],
)

rpm(
    name = "rpm-libs-0__4.16.1.3-22.el9.aarch64",
    sha256 = "86dd7d197a941c266491b00fae0a66e710ed1e1027d687a4b8c899a3b327ff24",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/rpm-libs-4.16.1.3-22.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/86dd7d197a941c266491b00fae0a66e710ed1e1027d687a4b8c899a3b327ff24",
    ],
)

rpm(
    name = "rpm-libs-0__4.16.1.3-22.el9.x86_64",
    sha256 = "cb46344dffa44265ec567715a0468e46d4c8ff7d1bfab104f3bf01c4e870af5a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/rpm-libs-4.16.1.3-22.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/cb46344dffa44265ec567715a0468e46d4c8ff7d1bfab104f3bf01c4e870af5a",
    ],
)

rpm(
    name = "rpm-plugin-selinux-0__4.16.1.3-22.el9.aarch64",
    sha256 = "58098139ab63a92b63ad99dca6e5d066336581a8377678dd82de34d2a602e4c9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/rpm-plugin-selinux-4.16.1.3-22.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/58098139ab63a92b63ad99dca6e5d066336581a8377678dd82de34d2a602e4c9",
    ],
)

rpm(
    name = "rpm-plugin-selinux-0__4.16.1.3-22.el9.x86_64",
    sha256 = "a980579de68b90527187b903950cf5e5cf2ef99d5f12939adad1419926216771",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/rpm-plugin-selinux-4.16.1.3-22.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/a980579de68b90527187b903950cf5e5cf2ef99d5f12939adad1419926216771",
    ],
)

rpm(
    name = "seabios-0__1.16.1-1.el9.x86_64",
    sha256 = "eec7c900965dfee16c97a341374c4592d5d194694f9a4af998be3f1e56f6bbad",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/seabios-1.16.1-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/eec7c900965dfee16c97a341374c4592d5d194694f9a4af998be3f1e56f6bbad",
    ],
)

rpm(
    name = "seabios-bin-0__1.16.1-1.el9.x86_64",
    sha256 = "bc66dda921365d3e1c99a989c4e7344bb1bebf7da34af910741dff599a2a950c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/seabios-bin-1.16.1-1.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/bc66dda921365d3e1c99a989c4e7344bb1bebf7da34af910741dff599a2a950c",
    ],
)

rpm(
    name = "seavgabios-bin-0__1.16.1-1.el9.x86_64",
    sha256 = "3032204d68939ad64b7f245adf578c75c9d7f8ed579cf2f06a77d4d97e57a966",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/seavgabios-bin-1.16.1-1.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/3032204d68939ad64b7f245adf578c75c9d7f8ed579cf2f06a77d4d97e57a966",
    ],
)

rpm(
    name = "sed-0__4.8-9.el9.aarch64",
    sha256 = "cfdec0f026af984c11277ae613f16af7a86ea6170aac3da495a027599fdc8e3d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/sed-4.8-9.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/cfdec0f026af984c11277ae613f16af7a86ea6170aac3da495a027599fdc8e3d",
    ],
)

rpm(
    name = "sed-0__4.8-9.el9.x86_64",
    sha256 = "a2c5d9a7f569abb5a592df1c3aaff0441bf827c9d0e2df0ab42b6c443dbc475f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/sed-4.8-9.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/a2c5d9a7f569abb5a592df1c3aaff0441bf827c9d0e2df0ab42b6c443dbc475f",
    ],
)

rpm(
    name = "selinux-policy-0__38.1.11-2.el9.aarch64",
    sha256 = "49ae94030bfea9d64003ca1c6e69dac20f5cdcf8fade3e7e2adc58a3c6110031",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/selinux-policy-38.1.11-2.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/49ae94030bfea9d64003ca1c6e69dac20f5cdcf8fade3e7e2adc58a3c6110031",
    ],
)

rpm(
    name = "selinux-policy-0__38.1.11-2.el9.x86_64",
    sha256 = "49ae94030bfea9d64003ca1c6e69dac20f5cdcf8fade3e7e2adc58a3c6110031",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/selinux-policy-38.1.11-2.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/49ae94030bfea9d64003ca1c6e69dac20f5cdcf8fade3e7e2adc58a3c6110031",
    ],
)

rpm(
    name = "selinux-policy-targeted-0__38.1.11-2.el9.aarch64",
    sha256 = "e3bad293af76aadedb0a8b8d8129d1db7bf96a1763f52c7002977d234eeca6d7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/selinux-policy-targeted-38.1.11-2.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/e3bad293af76aadedb0a8b8d8129d1db7bf96a1763f52c7002977d234eeca6d7",
    ],
)

rpm(
    name = "selinux-policy-targeted-0__38.1.11-2.el9.x86_64",
    sha256 = "e3bad293af76aadedb0a8b8d8129d1db7bf96a1763f52c7002977d234eeca6d7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/selinux-policy-targeted-38.1.11-2.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/e3bad293af76aadedb0a8b8d8129d1db7bf96a1763f52c7002977d234eeca6d7",
    ],
)

rpm(
    name = "setup-0__2.13.7-9.el9.aarch64",
    sha256 = "e1b7458eff8a50015cdfaef129aeebf663ffd70a5b94f4e3318a7603023de8ae",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/setup-2.13.7-9.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/e1b7458eff8a50015cdfaef129aeebf663ffd70a5b94f4e3318a7603023de8ae",
    ],
)

rpm(
    name = "setup-0__2.13.7-9.el9.x86_64",
    sha256 = "e1b7458eff8a50015cdfaef129aeebf663ffd70a5b94f4e3318a7603023de8ae",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/setup-2.13.7-9.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/e1b7458eff8a50015cdfaef129aeebf663ffd70a5b94f4e3318a7603023de8ae",
    ],
)

rpm(
    name = "shadow-utils-2__4.9-6.el9.aarch64",
    sha256 = "8d04bd9c627fdcfae1ff8a2ee8e4e75a6eb2391566a7cdfe89f6380c1cec06bf",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/shadow-utils-4.9-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/8d04bd9c627fdcfae1ff8a2ee8e4e75a6eb2391566a7cdfe89f6380c1cec06bf",
    ],
)

rpm(
    name = "shadow-utils-2__4.9-6.el9.x86_64",
    sha256 = "21eec2a59ddfe9976c24f8e5dcf8f8ffb4d565f4214325b88f32af935399bb93",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/shadow-utils-4.9-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/21eec2a59ddfe9976c24f8e5dcf8f8ffb4d565f4214325b88f32af935399bb93",
    ],
)

rpm(
    name = "snappy-0__1.1.8-8.el9.aarch64",
    sha256 = "02e5739b35acb3874546e98a8c182e1281f5a80604a550f05de2094c38c5e0d7",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/snappy-1.1.8-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/02e5739b35acb3874546e98a8c182e1281f5a80604a550f05de2094c38c5e0d7",
    ],
)

rpm(
    name = "snappy-0__1.1.8-8.el9.x86_64",
    sha256 = "10facee86b64af91b06292ca9892fd94fe5fc08c068b0baed6a0927d6a64955a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/snappy-1.1.8-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/10facee86b64af91b06292ca9892fd94fe5fc08c068b0baed6a0927d6a64955a",
    ],
)

rpm(
    name = "sqlite-libs-0__3.34.1-6.el9.aarch64",
    sha256 = "14ebed56d97af9a87504d2bf4c1c52f68e514cba6fb308ef559a0ed18e51d77f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/sqlite-libs-3.34.1-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/14ebed56d97af9a87504d2bf4c1c52f68e514cba6fb308ef559a0ed18e51d77f",
    ],
)

rpm(
    name = "sqlite-libs-0__3.34.1-6.el9.x86_64",
    sha256 = "440da6dd7ad99e29e540626efe09650add959846d00a9759f0c4a417161d911e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/sqlite-libs-3.34.1-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/440da6dd7ad99e29e540626efe09650add959846d00a9759f0c4a417161d911e",
    ],
)

rpm(
    name = "sssd-client-0__2.8.2-2.el9.aarch64",
    sha256 = "74c5cbe627200eb7996ac88a1a1269cb8fb5b2651f500a0b123a0e798579c047",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/sssd-client-2.8.2-2.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/74c5cbe627200eb7996ac88a1a1269cb8fb5b2651f500a0b123a0e798579c047",
    ],
)

rpm(
    name = "sssd-client-0__2.8.2-2.el9.x86_64",
    sha256 = "dea501258311ab21466fe23826b3da50c3191ff02a4093109c6fae6a03760882",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/sssd-client-2.8.2-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/dea501258311ab21466fe23826b3da50c3191ff02a4093109c6fae6a03760882",
    ],
)

rpm(
    name = "swtpm-0__0.8.0-1.el9.aarch64",
    sha256 = "7ccdddbd8dab7287094dddfee27e1791ffa9b8593611d90a68f9b5e3827389c3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/swtpm-0.8.0-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/7ccdddbd8dab7287094dddfee27e1791ffa9b8593611d90a68f9b5e3827389c3",
    ],
)

rpm(
    name = "swtpm-0__0.8.0-1.el9.x86_64",
    sha256 = "1828ddb3d6e0155b004eb2bc07c778b020509429cd3fae79ed20b533e06066c6",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/swtpm-0.8.0-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/1828ddb3d6e0155b004eb2bc07c778b020509429cd3fae79ed20b533e06066c6",
    ],
)

rpm(
    name = "swtpm-libs-0__0.8.0-1.el9.aarch64",
    sha256 = "27521263b75a6d3a69898b5300781ddd502b82b191f99a7bd450604e3def6db9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/swtpm-libs-0.8.0-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/27521263b75a6d3a69898b5300781ddd502b82b191f99a7bd450604e3def6db9",
    ],
)

rpm(
    name = "swtpm-libs-0__0.8.0-1.el9.x86_64",
    sha256 = "9afc462a3f5d36db313d3ebc4b09fc34f83b4e34419a1a8f738bcce03489d683",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/swtpm-libs-0.8.0-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/9afc462a3f5d36db313d3ebc4b09fc34f83b4e34419a1a8f738bcce03489d683",
    ],
)

rpm(
    name = "swtpm-tools-0__0.8.0-1.el9.aarch64",
    sha256 = "3f3624dbf8520a3bd46e2254b67b997eefbe8e2781753cd75b97876f0e396255",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/swtpm-tools-0.8.0-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/3f3624dbf8520a3bd46e2254b67b997eefbe8e2781753cd75b97876f0e396255",
    ],
)

rpm(
    name = "swtpm-tools-0__0.8.0-1.el9.x86_64",
    sha256 = "b3531cb8d1d4408945ae6ca072852d6a9cf82300061a263b11bd841cf51ea037",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/swtpm-tools-0.8.0-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/b3531cb8d1d4408945ae6ca072852d6a9cf82300061a263b11bd841cf51ea037",
    ],
)

rpm(
    name = "systemd-0__252-8.el9.aarch64",
    sha256 = "4024d2af966dcc6b8fd067f67331e1d681796f98f4903dac4ee4d00aa51ca21c",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/systemd-252-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/4024d2af966dcc6b8fd067f67331e1d681796f98f4903dac4ee4d00aa51ca21c",
    ],
)

rpm(
    name = "systemd-0__252-8.el9.x86_64",
    sha256 = "0b1e763e34adefbec11b780d30257435fdbd89c611d101f1e324e939d8dc1f46",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/systemd-252-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/0b1e763e34adefbec11b780d30257435fdbd89c611d101f1e324e939d8dc1f46",
    ],
)

rpm(
    name = "systemd-container-0__252-8.el9.aarch64",
    sha256 = "b574b8eb6dc0d4b5a4959fb762f7b245b116798b7af1a5191b88fa47ce65f7ce",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/systemd-container-252-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/b574b8eb6dc0d4b5a4959fb762f7b245b116798b7af1a5191b88fa47ce65f7ce",
    ],
)

rpm(
    name = "systemd-container-0__252-8.el9.x86_64",
    sha256 = "841cd74cfb5eafbfeb5b4864b5fde893f03c3a9ccc7ed5bd9cc630ac1359473b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/systemd-container-252-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/841cd74cfb5eafbfeb5b4864b5fde893f03c3a9ccc7ed5bd9cc630ac1359473b",
    ],
)

rpm(
    name = "systemd-libs-0__252-8.el9.aarch64",
    sha256 = "b82981c607ef59aa35901252b0884a493d10e844deee1bcd8a9255b40ab4e855",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/systemd-libs-252-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/b82981c607ef59aa35901252b0884a493d10e844deee1bcd8a9255b40ab4e855",
    ],
)

rpm(
    name = "systemd-libs-0__252-8.el9.x86_64",
    sha256 = "83e7ee151a97ebd01bede32dd35193892c70d34680fdaf87d00c77fd17c1bc91",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/systemd-libs-252-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/83e7ee151a97ebd01bede32dd35193892c70d34680fdaf87d00c77fd17c1bc91",
    ],
)

rpm(
    name = "systemd-pam-0__252-8.el9.aarch64",
    sha256 = "21b1aa08c08ca5e996d2811841f41aa42be82fb193873333fe175a45548d3123",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/systemd-pam-252-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/21b1aa08c08ca5e996d2811841f41aa42be82fb193873333fe175a45548d3123",
    ],
)

rpm(
    name = "systemd-pam-0__252-8.el9.x86_64",
    sha256 = "469f4594127a61486d9aee29fa584b141199454918843e7d9e87e011b540d56f",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/systemd-pam-252-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/469f4594127a61486d9aee29fa584b141199454918843e7d9e87e011b540d56f",
    ],
)

rpm(
    name = "systemd-rpm-macros-0__252-8.el9.aarch64",
    sha256 = "ac50989042a6cf07c9bc0e94787b3dc767ccc49b97a17a3851b6e8f2e615842a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/systemd-rpm-macros-252-8.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/ac50989042a6cf07c9bc0e94787b3dc767ccc49b97a17a3851b6e8f2e615842a",
    ],
)

rpm(
    name = "systemd-rpm-macros-0__252-8.el9.x86_64",
    sha256 = "ac50989042a6cf07c9bc0e94787b3dc767ccc49b97a17a3851b6e8f2e615842a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/systemd-rpm-macros-252-8.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/ac50989042a6cf07c9bc0e94787b3dc767ccc49b97a17a3851b6e8f2e615842a",
    ],
)

rpm(
    name = "tar-2__1.34-6.el9.aarch64",
    sha256 = "98a9ca5a25c6aa73b5183b3333abad062a8f82d8b9390d2b2fbdc1eea5b4fb9b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/tar-1.34-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/98a9ca5a25c6aa73b5183b3333abad062a8f82d8b9390d2b2fbdc1eea5b4fb9b",
    ],
)

rpm(
    name = "tar-2__1.34-6.el9.x86_64",
    sha256 = "9f6adb2da035d5123587a2bb401487521bd6543497003ffc6e66386d898133f3",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/tar-1.34-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/9f6adb2da035d5123587a2bb401487521bd6543497003ffc6e66386d898133f3",
    ],
)

rpm(
    name = "target-restore-0__2.1.75-1.el9.aarch64",
    sha256 = "b8cd2a141abaf56b14e1792ecacf5e60f43bb769c9a014cd518a528a46d7fe28",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/target-restore-2.1.75-1.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/b8cd2a141abaf56b14e1792ecacf5e60f43bb769c9a014cd518a528a46d7fe28",
    ],
)

rpm(
    name = "target-restore-0__2.1.75-1.el9.x86_64",
    sha256 = "b8cd2a141abaf56b14e1792ecacf5e60f43bb769c9a014cd518a528a46d7fe28",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/target-restore-2.1.75-1.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/b8cd2a141abaf56b14e1792ecacf5e60f43bb769c9a014cd518a528a46d7fe28",
    ],
)

rpm(
    name = "targetcli-0__2.1.53-7.el9.aarch64",
    sha256 = "a3a04950e17fa74236978efa7ff167ad8830fac3b74abc22af825cfcdeddde13",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/targetcli-2.1.53-7.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/a3a04950e17fa74236978efa7ff167ad8830fac3b74abc22af825cfcdeddde13",
    ],
)

rpm(
    name = "targetcli-0__2.1.53-7.el9.x86_64",
    sha256 = "a3a04950e17fa74236978efa7ff167ad8830fac3b74abc22af825cfcdeddde13",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/targetcli-2.1.53-7.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/a3a04950e17fa74236978efa7ff167ad8830fac3b74abc22af825cfcdeddde13",
    ],
)

rpm(
    name = "tzdata-0__2022g-2.el9.aarch64",
    sha256 = "083b9273251b720ebe7dbd54f98caf0727ca5019721c6fbabbbfca2e6cbe9097",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/tzdata-2022g-2.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/083b9273251b720ebe7dbd54f98caf0727ca5019721c6fbabbbfca2e6cbe9097",
    ],
)

rpm(
    name = "tzdata-0__2022g-2.el9.x86_64",
    sha256 = "083b9273251b720ebe7dbd54f98caf0727ca5019721c6fbabbbfca2e6cbe9097",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/tzdata-2022g-2.el9.noarch.rpm",
        "https://storage.googleapis.com/builddeps/083b9273251b720ebe7dbd54f98caf0727ca5019721c6fbabbbfca2e6cbe9097",
    ],
)

rpm(
    name = "unbound-libs-0__1.16.2-3.el9.aarch64",
    sha256 = "a8919b80ffaeae3d7a2247062bac1fbaf9de7c7e9aab5bd36181b758043ee2d0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/unbound-libs-1.16.2-3.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/a8919b80ffaeae3d7a2247062bac1fbaf9de7c7e9aab5bd36181b758043ee2d0",
    ],
)

rpm(
    name = "unbound-libs-0__1.16.2-3.el9.x86_64",
    sha256 = "db922b8fc89c38939f879d25909f6881ef736580925642fd3f4fbf8e93a7d139",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/unbound-libs-1.16.2-3.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/db922b8fc89c38939f879d25909f6881ef736580925642fd3f4fbf8e93a7d139",
    ],
)

rpm(
    name = "usbredir-0__0.13.0-2.el9.x86_64",
    sha256 = "7b6cec071b2d7437b70f8af875c127c00bd9b2e9d516ece64a9c30c96245394d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/usbredir-0.13.0-2.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7b6cec071b2d7437b70f8af875c127c00bd9b2e9d516ece64a9c30c96245394d",
    ],
)

rpm(
    name = "userspace-rcu-0__0.12.1-6.el9.aarch64",
    sha256 = "5ab924e8c35535d0101a5e1cb732e63940ef7b4b35a5cd0b422bf53809876b56",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/userspace-rcu-0.12.1-6.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/5ab924e8c35535d0101a5e1cb732e63940ef7b4b35a5cd0b422bf53809876b56",
    ],
)

rpm(
    name = "userspace-rcu-0__0.12.1-6.el9.x86_64",
    sha256 = "119e159428dda0e194c6428da57fae87ef75cce5c7271d347fe84283a7374c03",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/userspace-rcu-0.12.1-6.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/119e159428dda0e194c6428da57fae87ef75cce5c7271d347fe84283a7374c03",
    ],
)

rpm(
    name = "util-linux-0__2.37.4-10.el9.aarch64",
    sha256 = "d21f23042142e230fb1a2772233c0f29c9891015fb9ea4aa55a6906386eba994",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/util-linux-2.37.4-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/d21f23042142e230fb1a2772233c0f29c9891015fb9ea4aa55a6906386eba994",
    ],
)

rpm(
    name = "util-linux-0__2.37.4-10.el9.x86_64",
    sha256 = "4b8406b4e2590005261cc3f333b46e62fee299785db1fe6a4e135afddf7a674e",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/util-linux-2.37.4-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/4b8406b4e2590005261cc3f333b46e62fee299785db1fe6a4e135afddf7a674e",
    ],
)

rpm(
    name = "util-linux-core-0__2.37.4-10.el9.aarch64",
    sha256 = "20b5baca4a8a7d5ceb1287540ca29f81e6f056d9fb19ad1e869f83421fcb5b01",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/util-linux-core-2.37.4-10.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/20b5baca4a8a7d5ceb1287540ca29f81e6f056d9fb19ad1e869f83421fcb5b01",
    ],
)

rpm(
    name = "util-linux-core-0__2.37.4-10.el9.x86_64",
    sha256 = "cfbf12a58d9b739433ad4925d75401da9e898f9fac06b4eb32e023ce57db6e29",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/util-linux-core-2.37.4-10.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/cfbf12a58d9b739433ad4925d75401da9e898f9fac06b4eb32e023ce57db6e29",
    ],
)

rpm(
    name = "vim-minimal-2__8.2.2637-20.el9.aarch64",
    sha256 = "b142f0b4f853c0560a17f118cbffadd89d16296cac85287cd14d35bf8b0847f2",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/vim-minimal-8.2.2637-20.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/b142f0b4f853c0560a17f118cbffadd89d16296cac85287cd14d35bf8b0847f2",
    ],
)

rpm(
    name = "vim-minimal-2__8.2.2637-20.el9.x86_64",
    sha256 = "5bef7d6b66ece8820a758a6b1fb99a4512dd3bdcac0774723b630bfd5144ee62",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/vim-minimal-8.2.2637-20.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/5bef7d6b66ece8820a758a6b1fb99a4512dd3bdcac0774723b630bfd5144ee62",
    ],
)

rpm(
    name = "virtiofsd-0__1.5.0-1.el9.aarch64",
    sha256 = "ae8ab4d9506d3246cdf974549859d416a67f032a8ec0fa13e3f003c9ab700bb5",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/virtiofsd-1.5.0-1.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/ae8ab4d9506d3246cdf974549859d416a67f032a8ec0fa13e3f003c9ab700bb5",
    ],
)

rpm(
    name = "virtiofsd-0__1.5.0-1.el9.x86_64",
    sha256 = "c975314ab80b917ede3f7128470efd6954c2ed32f4a725719f140e7ef1668fcb",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/virtiofsd-1.5.0-1.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c975314ab80b917ede3f7128470efd6954c2ed32f4a725719f140e7ef1668fcb",
    ],
)

rpm(
    name = "which-0__2.21-29.el9.aarch64",
    sha256 = "2edd6b710ebd483724d0c0c1dff3d5922ce3082ea1bd10865d9f4f0bbf4bb050",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/which-2.21-29.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/2edd6b710ebd483724d0c0c1dff3d5922ce3082ea1bd10865d9f4f0bbf4bb050",
    ],
)

rpm(
    name = "which-0__2.21-29.el9.x86_64",
    sha256 = "c69af7b876363091bbeb99b4adfbab743f91da3c45478bb7a055c441e395174d",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/which-2.21-29.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/c69af7b876363091bbeb99b4adfbab743f91da3c45478bb7a055c441e395174d",
    ],
)

rpm(
    name = "xorriso-0__1.5.4-4.el9.aarch64",
    sha256 = "6b51217704ff76b372e5405a21206c646d0aa28ef12b46a8bdb933ebcaf4b7f9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/xorriso-1.5.4-4.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/6b51217704ff76b372e5405a21206c646d0aa28ef12b46a8bdb933ebcaf4b7f9",
    ],
)

rpm(
    name = "xorriso-0__1.5.4-4.el9.x86_64",
    sha256 = "f5f6e99d32dbe9d2db413ef294083a59b0161710cd1fc2623bb5e94f0abc2062",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/xorriso-1.5.4-4.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/f5f6e99d32dbe9d2db413ef294083a59b0161710cd1fc2623bb5e94f0abc2062",
    ],
)

rpm(
    name = "xz-0__5.2.5-8.el9.aarch64",
    sha256 = "c543b995056f118a141b499548ad00e566cc2062da2c36b2fc1e1b058c81dec1",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/xz-5.2.5-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/c543b995056f118a141b499548ad00e566cc2062da2c36b2fc1e1b058c81dec1",
    ],
)

rpm(
    name = "xz-0__5.2.5-8.el9.x86_64",
    sha256 = "159f0d11b5a78efa493b478b0c2df7ef42a54a9710b32dba9f94dd73eb333481",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/xz-5.2.5-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/159f0d11b5a78efa493b478b0c2df7ef42a54a9710b32dba9f94dd73eb333481",
    ],
)

rpm(
    name = "xz-libs-0__5.2.5-8.el9.aarch64",
    sha256 = "99784163a31515239be42e68608478b8337fd168cdb12bcba31de9dd78e35a25",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/xz-libs-5.2.5-8.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/99784163a31515239be42e68608478b8337fd168cdb12bcba31de9dd78e35a25",
    ],
)

rpm(
    name = "xz-libs-0__5.2.5-8.el9.x86_64",
    sha256 = "ff3c88297d75c51a5f8e9d2d69f8ad1eaf8347e20920b4335a3e0fc53269ad28",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/xz-libs-5.2.5-8.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/ff3c88297d75c51a5f8e9d2d69f8ad1eaf8347e20920b4335a3e0fc53269ad28",
    ],
)

rpm(
    name = "yajl-0__2.1.0-21.el9.aarch64",
    sha256 = "e40aede8c85585cf816078ddca50d0678ace4d326c99fa4d5a96413173fe652a",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/aarch64/os/Packages/yajl-2.1.0-21.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/e40aede8c85585cf816078ddca50d0678ace4d326c99fa4d5a96413173fe652a",
    ],
)

rpm(
    name = "yajl-0__2.1.0-21.el9.x86_64",
    sha256 = "d159334f408022942e77f67322288d13c1d575a3af54512d4310310709b644d9",
    urls = [
        "http://mirror.stream.centos.org/9-stream/AppStream/x86_64/os/Packages/yajl-2.1.0-21.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/d159334f408022942e77f67322288d13c1d575a3af54512d4310310709b644d9",
    ],
)

rpm(
    name = "zlib-0__1.2.11-39.el9.aarch64",
    sha256 = "a8772b0b74d78888d34ad995147dd4bb75f1b7528f214938ab5bcb5e68af08a0",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/aarch64/os/Packages/zlib-1.2.11-39.el9.aarch64.rpm",
        "https://storage.googleapis.com/builddeps/a8772b0b74d78888d34ad995147dd4bb75f1b7528f214938ab5bcb5e68af08a0",
    ],
)

rpm(
    name = "zlib-0__1.2.11-39.el9.x86_64",
    sha256 = "7a455be94959f587ceed90393b84e533039c56f0ef93c8e7bb6de7a934a7010b",
    urls = [
        "http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/Packages/zlib-1.2.11-39.el9.x86_64.rpm",
        "https://storage.googleapis.com/builddeps/7a455be94959f587ceed90393b84e533039c56f0ef93c8e7bb6de7a934a7010b",
    ],
)
