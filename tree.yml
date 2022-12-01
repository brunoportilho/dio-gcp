provider "google" {
  project = "XPTO-Corp"
  region  = "us-central1"
  zone    = "us-central1-c"
  credentials = "${file("serviceaccount.yaml")}"
}

resource "google_folder" "Hospitality" {
  display_name = "Hospitality"
  parent       = "organizations/<ID>"
}

resource "google_folder" "Banking" {
  display_name = "Banking"
  parent       = "organizations/<ID>"
}

resource "google_folder" "Developers" {
  display_name = "Developers"
  parent       = google_folder.Hospitality.name
}

resource "google_folder" "Support" {
  display_name = "Support"
  parent       = google_folder.Hospitality.name
}

resource "google_folder" "Comercial" {
  display_name = "Comercial"
  parent       = google_folder.Hospitality.name
}

resource "google_folder" "dev" {
  display_name = "dev"
  parent       = google_folder.Developers.name
}

resource "google_folder" "prod" {
  display_name = "prod"
  parent       = google_folder.Developers.name
}

resource "google_project" "x-module-dev" {
  name        = "ymodule-dev"
  project_id  = "ymodule-dev"
  folder_id   = google_folder.dev.name
  auto_create_network = false
  billing_account = "<BILLING-ACC-ID>"

}
